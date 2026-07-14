---
name: authz-and-audit-log
description: Implements RBAC authorization and immutable audit logging patterns, primarily for FastAPI/PostgreSQL stacks.
category: coding
tags: [coding, auth, rbac, audit-log, fastapi, postgresql, security]
agents: [opencode, freebuff, antigravity, codex]
---

# authz-and-audit-log

## Purpose

Provides implementation patterns for role-based access control (RBAC) and immutable audit logging in backend systems. FastAPI/PostgreSQL is the primary reference stack, but principles apply broadly.

## Invocation

**OpenCode / Codex:** `Invoke authz-and-audit-log`
**Freebuff:** `/skill authz-and-audit-log`

## RBAC Pattern

```python
# Role model
class Role(str, Enum):
    admin = "admin"
    editor = "editor"
    viewer = "viewer"

# Dependency
def require_role(required: Role):
    def checker(current_user: User = Depends(get_current_user)):
        if current_user.role != required:
            raise HTTPException(403, "Insufficient permissions")
        return current_user
    return checker

# Usage
@router.delete("/resource/{id}")
async def delete_resource(id: int, _=Depends(require_role(Role.admin))):
    ...
```

## Audit Log Pattern

```python
# Immutable audit log table
CREATE TABLE audit_log (
    id BIGSERIAL PRIMARY KEY,
    timestamp TIMESTAMPTZ NOT NULL DEFAULT now(),
    actor_id UUID NOT NULL,
    action VARCHAR(64) NOT NULL,
    resource_type VARCHAR(64),
    resource_id TEXT,
    before_state JSONB,
    after_state JSONB
);
-- No UPDATE or DELETE allowed on audit_log
```

## Workflow Steps

1. **Identify resources** that require access control.
2. **Define roles** and their permission sets.
3. **Implement RBAC dependencies** at the route level.
4. **Add audit log writes** to every state-changing endpoint.
5. **Test** each role combination for correct allow/deny behavior.
6. **Verify** audit log is append-only (no update/delete permissions on the table).

## Inputs

- API route list with intended access levels
- User model and existing auth implementation
- Database schema (if extending existing system)

## Outputs

- RBAC role definitions and middleware/dependency code
- Audit log table migration
- Audit log write integration at each protected endpoint
- Test cases for each role/permission combination

## Failure Modes

- **Existing auth uses a different model** (e.g., attribute-based) — adapt the pattern rather than replacing wholesale; flag the mismatch.

## Companion Skills

- `security-audit` — finds missing auth controls to implement
- `tdd-loop` — write role-permission tests
