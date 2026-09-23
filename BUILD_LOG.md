# Build log

Built with Claude (Anthropic) as a pair programmer. I set the scope, made the product calls and reviewed every version. Claude wrote most of the code.

## Cast

**V1. Prove the idea.** Three openings, one main line each, one sentence per move, plus a mode where you play the moves yourself. Cartoon style.
Feedback: the board and art felt built for a five-year-old.

**V2. Grown-up poster style.** Two-colour print art, condensed type, flat pieces.
Feedback: cleaner, but it had no warmth.

**V3. Hand-inked style.** Parchment, ink-wash textures, hatched pieces and a painted perspective board for each opening. Expanded from 3 to 10 openings once the first three felt right.

**V4. Retention.** Openings grouped by colour. Learned and Mastered stamps saved on the device. Clean-run scoring, a Next opening button, swipe to step, and a phone layout that keeps the buttons under the board.

**V5. Blind mode.** Play the line with no notes and no move hints. A clean blind run earns Mastered.

## Turning Point

**V1. Engine spike.** Stockfish 10 in a Web Worker, tested on a 33-move game. Depth 11 finished in about 4 seconds, so a full game fits under a minute. Latency was the biggest risk, so I tested it before any design.

**V2. First design.** Green brand style with rounded cards.
Feedback: the green background felt generic.

**V3. Premium redesign.** White page, black type, one green accent. A live example board in the hero, so the product explains itself.

**V4. Phone first.** Verdict above the board on phones, a tappable move list, swipe to step through moves.

**V5. Missed chances.** Flags moves where your opponent slipped and you didn't punish it. Clearer wording when the best move was mate.

## Decisions I'd defend in a review

- No accuracy score as the headline. It never matches Chess.com and it flatters won positions.
- PGN upload before Chess.com import. Chess.com has no single-game endpoint, so import needs a server.
- One line per opening. A variation tree turns Cast into a worse Lichess.
