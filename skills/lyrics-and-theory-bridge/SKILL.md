---
name: lyrics-and-theory-bridge
description: Bridges lyric writing with music theory concepts — chord progressions, modal harmony, rhythmic cadence, and melodic phrasing — for composition, arrangement, and songwriting workflows.
category: media
tags: [lyrics, music-theory, songwriting, composition, arrangement, hip-hop]
agents: [opencode, freebuff, antigravity, codex]
---

# lyrics-and-theory-bridge

## Purpose

Connects the craft of lyric writing to underlying music theory. When writing lyrics, the theoretical structure of the backing track (key, mode, chord progression, rhythmic feel) shapes what syllable patterns, rhyme schemes, and melodic contours will land. This skill teaches agents to move fluidly between lyric and theory domains — suggesting harmonic contexts for lyrical ideas, explaining why a lyric feels "off" in a given key, and proposing rewrites that align better with the music's emotional arc.

Primary context: hip-hop, underground rap, experimental music. Secondary applicability to any genre involving melody + lyric composition.

## Invocation

**OpenCode / Codex:** `Invoke lyrics-and-theory-bridge`
**Freebuff:** `/skill lyrics-and-theory-bridge`

Natural language triggers:
- "Help me write a verse for this chord progression"
- "Why does this lyric feel off over this beat?"
- "What key is this sample in and what rhyme schemes fit?"
- "Suggest a bridge that resolves this harmonic tension"
- "Analyse the flow and cadence of these lyrics"
- "Map this vocal melody to the chord changes"

## Workflow Steps

1. **Establish harmonic context:** Identify or confirm the key, mode, tempo, and chord progression of the underlying music.
2. **Analyse existing lyrics (if provided):** Scan for rhyme scheme (AABB, ABAB, internal, multisyllabic), cadence alignment with the beat grid, and syllable stress patterns.
3. **Identify friction points:** Flag syllables that land on weak beats when they should land strong, rhymes that feel forced, or melodic contours that clash with the chord's tension/resolution cycle.
4. **Propose theory-informed rewrites:** Suggest lyric alternatives that align stress with downbeats, place resolution syllables on root-note chords, and exploit the mode's characteristic intervals for emotional colour.
5. **Suggest complementary musical moves:** If the lyric demands a lift or drop, suggest chord substitutions or rhythmic variations that support it.
6. **Document:** Log session decisions to `obsidian-music-journal` if working within an active project.

## Music Theory Reference (Hip-Hop / Underground Context)

### Common Modes and Their Lyrical Affect
| Mode | Character | Hip-Hop Use Case |
|---|---|---|
| Dorian | Minor but hopeful, soulful | Boom bap, conscious rap |
| Aeolian (Natural Minor) | Dark, melancholic | Trap, introspective |
| Mixolydian | Bluesy, grounded | Funk-influenced, lo-fi |
| Phrygian | Tense, aggressive, Spanish tinge | Drill, experimental, dark trap |
| Lydian | Dreamy, floating, unresolved | Abstract, experimental |

### Rhythmic Cadence Patterns
- **On-beat flow:** Stresses land on beats 1, 2, 3, 4. Stable, declarative.
- **Syncopated flow:** Stresses fall between beats. Creates urgency or playfulness.
- **Double-time feel:** Twice the syllable density per bar. Raises intensity.
- **Laid-back (behind-the-beat):** Syllables start fractionally late. Creates relaxed or menacing weight.

### Rhyme Scheme Guidance
- **Multisyllabic rhymes** over monosyllabic — richer, harder to detect consciously.
- **Internal rhymes** carry a bar forward and reward repeat listening.
- **Consonance over perfect rhyme** at phrase endings — more natural speech rhythm.

## Inputs

- Lyric draft (partial or complete bar/verse/hook)
- Harmonic context: key, chord progression, mode, and/or sample identification
- Tempo (BPM) and time signature if rhythmic analysis is needed
- Intent/mood for the section (aggressive, introspective, celebratory, unresolved)

## Outputs

- Annotated lyric analysis: rhyme scheme map, cadence alignment assessment, friction points flagged
- Rewrite suggestions with theory rationale for each change
- Chord substitution or rhythmic variation suggestions where musically appropriate
- Optional: Obsidian note created in `Music Projects/<project>/lyrics.md` via `obsidian-music-journal`

## Safety

- Never rewrite lyrics without presenting the original and diff side-by-side — artist intent is primary.
- Do not force genre conventions onto the writer; present theory as options, not rules.
- If sample-clearing or copyright issues are relevant, flag them but do not attempt to give legal advice.

## Failure Modes

- **No harmonic context provided** — request key/chord info before attempting theory alignment; do not guess the key and silently apply it.
- **Lyrics in a language other than English** — cadence and stress analysis may be unreliable; flag and ask user for language-specific guidance.
- **Abstract / intentionally arrhythmic lyrics** — apply theory suggestions lightly; experimental work may deliberately break rules. Ask before rewriting.
- **Conflicting musical signals** — if the sample is in an ambiguous key (b7 vs natural 7), surface both interpretations before proceeding.

## References

- Adam Neely (music theory + hip-hop): https://www.youtube.com/@AdamNeely
- 12tone (theory applied to popular music): https://www.youtube.com/@12tonevideos
- Open Music Theory: https://openmusictheory.github.io/
- Hooktheory (chord progression analysis): https://www.hooktheory.com/
- RapPad (rhyme assistant): https://www.rappad.co/

## Companion Skills

- `music-project-planner` — active production project context
- `obsidian-music-journal` — log session notes and drafts to vault
- `dj-set-architect` — harmonic mixing context for transitions between tracks
- `dj-library-curator` — key/mode metadata for backing tracks
