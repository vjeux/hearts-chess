# ♥ 3-Hearts Chess — Rules

A chess variant where every piece has **hearts** and can survive being attacked — until it can't.

## The Board

Standard 8×8 chess board, standard starting position, standard piece movement
(pawns, knights, bishops, rooks, queens, and kings all move exactly as in normal chess,
including castling, en passant, and pawn promotion).

## Hearts

- **Every piece starts with 3 hearts** (♥♥♥), shown above the piece.
- Hearts are how a piece survives attacks. A normal chess piece dies the moment it's
  captured; here, pieces can take a few hits first.

## The Damage Phase

**At the end of every move, damage is applied — but only to the *opponent* of the player
who just moved.** (The side that just moved never takes damage on its own turn.)

For each of the opponent's pieces:

- **It loses one heart for every enemy piece currently attacking it.**
  - Attacked by one piece → lose 1 heart.
  - Attacked by two pieces → lose 2 hearts.
  - Attacked by three pieces → lose 3 hearts, and so on.
- **A piece at 0 hearts is removed** from the board.

Defending a piece does **not** stop it from losing hearts — defense only matters for
recapture math in your head. If your piece is attacked, it *will* lose hearts.

## Capturing

You can still **capture normally** — move onto an enemy square and take the piece outright,
regardless of how many hearts it had. Both mechanics coexist:

- Landing on a piece = instant capture (all hearts gone at once).
- Being left under attack at end of a move = lose one heart per attacker.

## The King

The king also has **3 hearts**, with two important differences:

1. **You still cannot move your king into check** (standard rule), and
   **checkmate still ends the game immediately.**
2. Because you can never leave your own king in check, your king only ever takes damage
   from the **opponent's checking move** — so it loses exactly **one heart per check**.

## How to Win

There are **two ways to win**:

1. **Checkmate** your opponent's king (as in normal chess), **or**
2. **Check your opponent's king three times** — each check drains one of its hearts,
   and at 0 hearts that player loses.

(A rare double-check drains 2 hearts at once, since the king is attacked by two pieces.)

## Draws

- Stalemate (no legal moves, not in check).
- 50-move rule.
- Only kings remain with no way to make progress.

## The Bot

The opponent is a ~1000-rated bot that understands the heart mechanic: it values fragile
low-heart pieces less, avoids leaving its own king exposed to checks, and hunts checks
against your king to chip away its hearts — while still making human-like mistakes.
