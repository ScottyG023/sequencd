# SEQUENCD - Claude Code Context

## Overview
Daily number sequence puzzle game at **sequencd.com.au**. Users guess the missing number in a sequence. One puzzle per day, Wordle-style sharing.

## Deployment
- **Hosted on:** GitHub Pages (auto-deploys on push to main)
- **Repo:** `github.com:ScottyG023/sequencd.git`
- **Domain:** sequencd.com.au (configured via CNAME file)

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Complete game - HTML, CSS, JS all embedded (~100KB) |
| `puzzles.json` | All puzzles in JSON array (currently 200+ puzzles) |
| `CNAME` | Custom domain config for GitHub Pages |
| `manifest.json` | PWA manifest for mobile install |
| `og-image.png` | Social sharing preview image |

## Puzzle Format

```json
{
  "sequence": [1, 2, 4, 8, 15, 26, 42],
  "blankIndex": 3,
  "answer": 8,
  "pattern": "Cake numbers",
  "difficulty": 3,
  "hint1": "Slicing a cake in 3D",
  "hint2": "Maximum pieces with n cuts"
}
```

### Fields:
- **sequence**: Full sequence including the answer
- **blankIndex**: 0-indexed position of the hidden number
- **answer**: The correct answer (must match sequence[blankIndex])
- **pattern**: Shown after solving (or final wrong guess)
- **difficulty**: 1-5 stars
- **hint1/hint2**: Progressive hints shown after wrong guesses

### Puzzle Selection
Puzzles are selected by date - puzzle number = days since launch. The array index determines which day a puzzle appears.

## Common Tasks

### Edit a puzzle
1. Find puzzle in `puzzles.json` (search by pattern name or sequence)
2. Edit the fields
3. Commit and push - changes go live immediately

### Add a new puzzle
Add to the puzzles array in `puzzles.json`. New puzzles appear on future dates based on array position.

### Check puzzle difficulty
When setting `blankIndex`, consider how many plausible guesses exist between surrounding numbers. Middle positions are harder than edges.

## Design Decisions

- **blankIndex positioning**: Avoid positions where the answer is trivially constrained (e.g., between 1 and 4 leaves only 2-3 options). Prefer positions with wider gaps.
- **No build step**: Everything is vanilla HTML/CSS/JS for simplicity
- **Mobile-first**: Touch-friendly number pad, responsive design

## Useful Sequences Reference

| Pattern | Example | Formula |
|---------|---------|---------|
| Fibonacci | 1,1,2,3,5,8,13 | F(n) = F(n-1) + F(n-2) |
| Triangular | 1,3,6,10,15,21 | n(n+1)/2 |
| Square | 1,4,9,16,25,36 | n² |
| Cube | 1,8,27,64,125 | n³ |
| Cake (3D) | 1,2,4,8,15,26,42 | (n³+5n+6)/6 |
| Lazy Caterer (2D) | 1,2,4,7,11,16,22 | (n²+n+2)/2 |
| Factorials | 1,2,6,24,120,720 | n! |
| Primes | 2,3,5,7,11,13,17 | - |

## Notes
- Scotty is in Sydney (AEST/AEDT timezone)
- New puzzle appears at midnight local time for each user
- Stats stored in browser localStorage
