# SEQUENCD

A viral daily number sequence puzzle game. Find the missing number!

## Play

Open `index.html` in any modern browser. No build step required.

## How It Works

- One puzzle per day, same for everyone worldwide
- Find the missing number in a sequence of 6-8 numbers
- 3 attempts to guess correctly
- Feedback: Green (correct), Yellow (close), Red (wrong with hint)
- Share your results with friends

## Sequence Types

The game includes 130+ unique puzzles featuring:

- **Basic**: Add 2, count by 5s, count by 10s
- **Multiplication**: Powers of 2, double each time, multiply by 3
- **Mathematical**: Fibonacci, primes, squares, cubes, triangular numbers
- **Advanced**: Factorials, look-and-say, multiply previous two
- **Fun**: Digits of Pi, currency denominations, clock patterns

## Difficulty Rating

Each puzzle is rated 1-5 stars:
- ⭐ Simple counting/addition
- ⭐⭐ Multiplication patterns
- ⭐⭐⭐ Fibonacci, squares, triangular
- ⭐⭐⭐⭐ Primes, factorials, complex patterns
- ⭐⭐⭐⭐⭐ Mathematical constants, advanced sequences

## Features

- **Daily Puzzle**: New puzzle at midnight (local time)
- **Streak Tracking**: Build consecutive day streaks
- **Statistics**: Games played, win %, current/max streak, guess distribution
- **Dark Mode**: Toggle between light and dark themes
- **Share Results**: Wordle-style shareable results
- **Mobile-First**: Responsive design with touch-friendly number pad
- **Offline Ready**: Works without internet after first load
- **No Build Step**: Single HTML file with embedded CSS/JS

## Share Format

```
SEQUENCD #42 ⭐⭐⭐
🟩 1/3

2, 4, 8, __, 32, 64
Pattern: Powers of 2

sequencd.com
```

## Technical Details

- **Storage**: LocalStorage for game state and stats
- **Puzzle Selection**: Date-seeded deterministic selection
- **No Dependencies**: Pure vanilla HTML/CSS/JS
- **File Size**: ~30KB total

## File Structure

```
sequencd/
├── index.html      # Complete game (HTML + CSS + JS)
├── puzzles.json    # 130+ pre-generated puzzles
└── README.md       # This file
```

## Customization

### Adding Puzzles

Edit `puzzles.json` to add new puzzles:

```json
{
  "sequence": [2, 4, 8, 16, 32, 64],
  "blankIndex": 3,
  "answer": 16,
  "pattern": "Powers of 2",
  "difficulty": 2
}
```

### Styling

CSS variables in `index.html` for theming:

```css
:root {
    --primary: #6B5B95;      /* Main purple */
    --success: #4CAF50;      /* Correct green */
    --warning: #FF9800;      /* Close yellow */
    --error: #f44336;        /* Wrong red */
}
```

## Deployment

1. Upload all files to any static hosting (Netlify, Vercel, GitHub Pages)
2. No server-side code required
3. Works from any subdirectory

## Browser Support

- Chrome 60+
- Firefox 55+
- Safari 11+
- Edge 79+

## License

MIT

---

Made with math and caffeine.
