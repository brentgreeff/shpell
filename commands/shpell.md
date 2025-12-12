---
argument-hint: [path]
description: Spell check files using typos-cli with false positive filtering. When Claude needs to check spelling, find typos, or verify prose quality in markdown, code, or documentation.
---

# Spell Check

Check spelling using `typos` and filter false positives.

## Instructions

1. Check if typos is installed:
```bash
command -v typos
```
If not installed, ask: "typos-cli not found. Install it? (`brew install typos-cli`)"

2. If no path provided, ask: "What should I check? (e.g., `website/src/blog/`, `.`, specific file)"

3. Run the spell checker:
```bash
typos <path> 2>&1
```

4. Interpret results:
   - Show findings grouped by file
   - Flag likely **false positives**: code terms, proper nouns, technical jargon
   - Flag likely **real typos**: common misspellings, transposed letters

5. For each finding, suggest:
   - Fix it (show the correction)
   - Ignore it (add to `.typos.toml` if persistent)

6. Offer to auto-fix real typos:
```bash
typos --write-changes <path>
```

## False Positive Patterns

These are often NOT typos:
- camelCase/snake_case identifiers
- Package/library names
- File paths
- Technical acronyms
- Proper nouns (names, companies)

---

**Path:** $ARGUMENTS
