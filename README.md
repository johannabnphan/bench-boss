# Bench Boss

A free fantasy football lineup helper. Enter a Sleeper username and it recommends the best lineup for the weekly matchup, one player at a time.

The whole app is a single `index.html`, with no build step.

## What it does

- **Connects to Sleeper by username.** Bench Boss loads your leagues, your roster and this week's opponent.
- **Gives each player a verdict and reason.** Every lineup and bench player gets a verdict (Start, Keep, Toss-up, Sit, Close, Bench or Out), along with a short reason for it.
- **Shows exact live scores with projected finals.** Each player's live score appears in large type, with their projected final score underneath in smaller type.
- **Shows a Predicted winner line.** This line names the team expected to win the matchup, and by how much, using the combined Sleeper and ESPN projections.

## How it works

- **Sleeper data:** leagues, rosters, matchups, league scoring settings and the NFL player list all come from Sleeper's public API.
- **Combined projections:** Sleeper and ESPN projections are averaged. Sleeper's projections are recalculated with your league's scoring settings. If ESPN fails to load, Bench Boss falls back to Sleeper projections only.
- **Live scoring:** during games, scores refresh about every 45 seconds. Points from games that have already started are locked in. ESPN's scoreboard supplies game progress, so a player's remaining projection shrinks as their game goes on.
- **Injury and bye tags:** these come from Sleeper. The player list, which carries injury status, refreshes about every 30 minutes.
- **Per-player suggestions:** each player's projection range (floor to ceiling) is compared with the alternatives, taking the opponent into account. When you're the underdog, the picks lean toward upside. When you're favored, they lean toward safer floors.
- **Status chips:** chips show whether Sleeper projections, ESPN projections and live game status loaded. When a source fails, its chip's hover text explains why.

Note: Sleeper's projections endpoint is unofficial and may change.

## Disclaimer

Bench Boss is a free project made for fun. It is not affiliated with, endorsed by or sponsored by Sleeper, ESPN or the NFL.
