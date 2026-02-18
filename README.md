# PFL Academy — State Simple Data 2026

## Repository Structure

```
/states/                          ← 35 corrected state .md files (drop-in replacements)
/chapters/
  /LC-36/                         ← Combined Gambling chapter (L-36 + L-37)
    architecture.json             ← Chapter config, state usage, source file locations
  /LC-39/                         ← Combined Philanthropy chapter (L-39 + L-40)
    architecture.json             ← Chapter config, state usage, source file locations
/COMPLETE-STATE-CORRECTIONS-MASTER.md  ← Full documentation of all fixes
/CHAPTER-MANIFEST.md              ← Complete chapter inventory (L-01 to L-69 + LC-36 + LC-39)
```

## What Was Fixed

**299 corrections across 35 state files:**

- **Systemic title cascade** — Career chapters L-41 through L-46 had titles shifted by one position across ALL states. "Professional Development" was a hallucinated title that appeared in every file. All titles now match canonical L-chapter names.
- **12 duplicate L-chapter mappings** — Resolved across Delaware, Florida, Illinois, Kentucky, Minnesota, Mississippi, New Jersey, North Carolina, Oregon, Pennsylvania, Rhode Island, Virginia
- **4 complete state rebuilds** — Texas-PFL, Texas-PFLE, Mississippi, Rhode Island (files were too broken for incremental fixes)
- **1 missing chapter restored** — Delaware was missing L-31 (Renting), Florida was missing L-31, North Carolina was missing L-9 (Tax Deductions)

## Combined Chapters (LC-36 and LC-39)

Two pairs of core chapters have combined versions used by 30 states:

| Chapter | Merges | Used By |
|---------|--------|---------|
| **LC-36** | L-36 (Gambling Risks) + L-37 (Gambling Costs/Benefits) | 30 states |
| **LC-39** | L-39 (Charitable Giving) + L-40 (Checking Charitable Groups) | 30 states |

Combined chapters free curriculum slots for extended chapters (L-46, L-47).

### States Using SEPARATE Chapters (NOT Combined)
California, Illinois, Indiana, North Carolina, Rhode Island

### Georgia Exception
Georgia uses L-36/L-37 **separate** but L-39+L-40 **combined**.

### Source Files to Copy
The slide decks for LC-36 and LC-39 currently live in a different repo and need to be copied here:

**Source repo:** `pfl-academy-sync-90`
**Source branch:** `claude/add-state-variables-slides-017dH4k6D8oq1Qu7NjHgPmmD`
**Source path:** `/slide-decks/`

Copy these files into `/chapters/LC-36/` and `/chapters/LC-39/`:
- `LC-36-combined-gambling-slides.html` → `/chapters/LC-36/`
- `LC-39-combined-philanthropy-slides.html` → `/chapters/LC-39/`
- `L-46-automobile-finance-slides.html` → (already in L-46 chapter dir)
- `CHAPTER_RESOURCES_L46-LC39.md` → `/chapters/` (shared resource doc)

### Content Still Needed for LC-36 and LC-39
The combined chapters have slide decks (Day 1) completed. Still needed:
- Day 2 Student Workbooks (merge from L-36+L-37 and L-39+L-40 respectively)
- Day 1 and Day 2 Teacher Guides
- Free Resource PDFs (Student Workbook PDF, Teacher Guide PDF)
- Question banks / assessment items

See `architecture.json` in each LC directory for full status.

## Mapping Format Reference

Each state file contains an `L_CHAPTER_MAPPINGS:` line in this format:
```
L_CHAPTER_MAPPINGS: L-1→1.1|L-2→1.2|...|L-36+L-37→8.1|L-39+L-40→8.2
```

- `L-XX→X.X` = Individual chapter mapped to position
- `L-36+L-37→X.X` = Combined chapter (serves LC-36 content)
- `L-39+L-40→X.X` = Combined chapter (serves LC-39 content)
- Arrow character is `→` (Unicode U+2192)

## Validation

All 35 state files pass these checks:
- ✅ `L_CHAPTER_MAPPINGS` line exists and is parseable
- ✅ Zero duplicate L-chapter numbers
- ✅ Zero "Professional Development" fake titles
- ✅ All core chapters L-1 through L-45 present (except Texas-PFLE which intentionally omits 8 per TEKS §113.76 scope)
- ✅ Chapter titles in `_CHAPTERS` lines match canonical names for their mapped L-chapter
- ✅ Arrow characters normalized to `→`
