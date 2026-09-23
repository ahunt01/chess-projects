# Chess projects

Two small chess products, built and scoped as a product manager would: find the core of each idea, cut the rest, and test the riskiest assumption first.

Live: `https://ahunt01.github.io/chess-projects/`

## 1. Cast (`/cast`)

Ten chess openings, each with a personality. The Italian Game is a polite duel. The Sicilian is a knife fight. You step through one main line with a one-sentence explanation per move, then play it yourself while the board answers with the book reply. Blind mode removes the notes and move hints. Progress (Learned, Mastered) saves on your device.

**The core:** a small cast of characters, one line each, one sentence per move.

**What I cut, and why:**
- Variation trees and "explore any move". Lichess already does this well. A tree turns this into a worse copy.
- Engine evaluations, popularity stats and ECO codes. They make it a database, not a character.
- Accounts and progress tracking. Nothing to validate there yet.

**The risk I tested first:** does the concept feel fun, or does it feel like a board in a costume? I built three openings before writing the other seven.

## 2. Turning Point (`/turning-point`)

Paste or drop a PGN. Stockfish runs in the browser, grades every move, and gives one verdict: the move where the game turned. It also flags chances you missed after your opponent's mistakes.

**The core:** one decisive moment, shown on the board, for a player who won't study a classification table.

**Decisions:**
- **No accuracy score as the headline.** A single percentage flatters won positions and never matches Chess.com's number. It sits at the bottom with a note.
- **Only three labels:** inaccuracy, mistake, blunder. "Brilliant" and "Great" are unstable at low depth.
- **Ask which side you played.** A PGN doesn't say, and guessing from the winner is wrong half the time.
- **PGN upload before Chess.com import.** Chess.com has no single-game endpoint, so import needs a server proxy. Upload covers the use case with zero backend.
- **Single-thread Stockfish in a Web Worker.** Multi-thread needs cross-origin isolation headers. Quick mode runs at depth 11 to keep a full game under a minute.

**The risk I tested first:** engine latency. If a full game took too long, the product would change to key moments only.

## Stack

Plain HTML, CSS and JavaScript. [chess.js](https://github.com/jhlywa/chess.js) for rules and PGN parsing. [Stockfish.js](https://github.com/nmrugg/stockfish.js) for analysis. No build step, no backend.

## Next

- Test both with five club players and record what confuses them.

See [BUILD_LOG.md](BUILD_LOG.md) for how each product changed and why.
- Cast: add practice streaks if people return to it.
- Cast: spaced repetition for openings you've learned but not mastered.
- Turning Point: Lichess URL import.
