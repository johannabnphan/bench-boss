# Bench Boss

A free fantasy football lineup helper. Enter a Sleeper username and it recommends the best lineup for the weekly matchup, one player at a time.

The whole app is a single `index.html`, with no build step.

## What it does

- **Connects to Sleeper by username or league.** Enter your username to load your leagues, roster and this week's opponent. Add an optional league name to open that league first. Or paste a league link or ID and pick your team from the list. (Sleeper has no search by league name across all of Sleeper, so a name works together with a username.)
- **Shows the whole league on one page.** A My matchup / Whole league switch at the top lists every matchup this week: both teams' live scores, projected finals and win chances, with a tap to see both lineups side by side. Standings are at the bottom.
- **Rates defenses and schedules.** Whole league has a Schedule strength section. Every NFL defense is rated by the fantasy points it has allowed per game to QBs, RBs, WRs and TEs this season (Sleeper's weekly stats scored with your league's settings, matched to ESPN's schedule), with the yards and TDs behind it. Rostered players are sorted from easiest to toughest next 4 weeks, with colour-coded opponents; you can view your team, any team or every rostered player. Once loaded, My matchup also adds a Matchup note for especially soft or tough opponents.
- **Analyzes your team and suggests trades.** A separate Trades page (the Trades option in the My matchup / Whole league switch) ranks your team at each position against the rest of your league, lists your needs and strengths, and suggests one-for-one trades that fill a need and also help the other team. A trade builder lets you pick players on both sides and see how each team's best weekly lineup changes. Points use the average Sleeper projection over this week and the next 3, with your league's scoring including bonuses. Every player shows a trade value (0–100, A–F) and how much of their weekly points come from bonuses, and the builder compares total value and bonus points on each side.
- **Gives each player a verdict and reason.** Every lineup and bench player gets a verdict (Start, Keep, Toss-up, Sit, Close, Bench or Out), along with a short reason for it.
- **Shows exact live scores with projected finals.** Each player's live score appears in large type, with their projected final score underneath in smaller type.
- **Puts both lineups side by side.** Your recommended lineup and your opponent's lineup sit next to each other, slot by slot, with live scores and projected finals.
- **Shows both benches.** Your bench and your opponent's sit side by side (stacked on phones). It flags any of their bench players who project more than one of their starters.
- **Watches your matchup.** A floating Watch button opens a pop-up that logs injury status changes (for your players and your opponent's starters), players who become worth starting, win-chance swings of 10 points or more, and live blowouts. The button shows how many new alerts you have, and you can turn on browser alerts for these.
- **Shows a crowd check.** Each player shows the "% start" figure from Sleeper (ESPN's start rate when Sleeper's isn't available), plus Sleeper's 24-hour add and drop counts. The Watch pop-up flags bench players most managers start and starters few managers start.
- **Shows the games that decide your matchup.** For each NFL game, the Watch pop-up shows how many projected points you and your opponent have left in it, the betting favorite or live win chance, and when your players face your opponent's defense.
- **Shows snap share.** Each player shows the share of their team's offensive snaps they played over the last 3 games, plus today's snap count during games. Players under 40% are flagged because they get fewer chances to score.
- **Shows team roles and opportunity.** Each player gets a role like WR1 or RB2, ranked by recent snap share (Sleeper's depth chart fills gaps). When a teammate at the same position who usually plays is out or doubtful, the player is flagged for more snaps and touches. This is a note only, because Sleeper and ESPN projections already adjust for announced injuries.
- **Gives each player a value score.** A 0–100 value with a letter grade (A–F) for this week. It blends the combined Sleeper and ESPN projection (ranked against everyone at the same position, 55%), snap share (15%), start % (15%), how closely Sleeper and ESPN agree (10%) and Sleeper add/drop trends (5%).
- **Counts bonus points.** Bench Boss reads your league's bonus scoring (100+ yard games, 300+ passing yards, long TDs, first downs, TE premium and more). It estimates each player's chance of hitting them, adds the expected bonus points to both Sleeper's and ESPN's projections, and notes likely bonuses under each player. A Bonus scoring section lists your league's bonuses and other common ones Sleeper and ESPN leagues use.
- **Keeps player details tidy.** Under each player: one line with the reason, a row of small chips (Sleeper and ESPN projections, whether the sources agree, role, snap share, start %, adds and drops), and short labelled notes for Game, Opportunity and Snaps.
- **Has a bit of fun.** The cursor is a small football, and every minute or two a football is kicked through a goalpost and "TD!" pops up. Tap the Bench Boss logo to kick one yourself. On phones, a little football pops wherever you tap. All of this is off when your device is set to reduce motion.
- **Shows a Predicted winner line.** This line names the team expected to win the matchup, and by how much, using the combined Sleeper and ESPN projections.

## How it works

- **Sleeper data:** leagues, rosters, matchups, league scoring settings and the NFL player list all come from Sleeper's public API.
- **Combined projections:** Sleeper and ESPN projections are averaged. Sleeper's projections are recalculated with your league's scoring settings. If ESPN fails to load, Bench Boss falls back to Sleeper projections only.
- **Live scoring:** during games, scores refresh about every 45 seconds. Points from games that have already started are locked in. ESPN's scoreboard supplies game progress, so a player's remaining projection shrinks as their game goes on.
- **Injury and bye tags:** these come from Sleeper. The player list, which carries injury status, refreshes about every 30 minutes.
- **Per-player suggestions:** each player's projection range (floor to ceiling) is compared with the alternatives, taking the opponent into account. When you're the underdog, the picks lean toward upside. When you're favored, they lean toward safer floors.
- **Game notes:** before kickoff, ESPN's betting line gives each team's chance to win. During games, ESPN's live win probability is used. Teams that fall behind tend to pass more and run less, so trailing teams' passers and receivers get garbage-time upside and their running backs get downside.
- **Watch and alerts:** each refresh is compared with the last one stored in your browser for that league and week. The first visit to a week only records a starting point. Alerts only work while the page is open in a tab; it keeps checking in a background tab when alerts are on. Some mobile browsers only allow alerts from installed apps.
- **Status chips:** chips show whether Sleeper projections, ESPN projections, live game status and Sleeper start % loaded. When a source fails, its chip's hover text explains why.

Note: Sleeper's projections, "% start" and weekly stats (snap counts) endpoints are unofficial and may change.

## Disclaimer

Bench Boss is a free project made for fun. It is not affiliated with, endorsed by or sponsored by Sleeper, ESPN or the NFL.
