# Scouting Profile Finder

## Concept

The Scouting Profile Finder is a planned feature for the Football Player Performance Analytics project.

The idea is to simulate a data-driven scouting process. Instead of simply asking “who is the best player?”, the feature helps answer a more specific question:

> Which player best fits the profile we are looking for?

For example, a club may need a center back who is strong defensively, comfortable with long passes, good at progressing the ball, and reliable in aerial duels. The system would allow the user to define this target profile and return a ranked list of players who best match those characteristics.

## How It Would Work

The user would select:

1. A position or role, such as center back, midfielder, winger, or striker.
2. The most relevant performance metrics for that role.
3. The importance, or weight, of each selected metric.

The system would then compare players within a similar position group, using normalized metrics such as per-90 values and position-based percentiles.

This makes the comparison fairer because different positions naturally perform better in different types of metrics. For example, forwards are expected to score more goals, while defenders are expected to contribute more through tackles, interceptions, clearances, and aerial duels.

## Example Use Case

A user looking for a ball-playing center back could prioritize:

- Progressive passes
- Long passing accuracy
- Passes into the final third
- Defensive actions
- Aerial duel success
- Low error rate

The system would calculate a scouting fit score and return a ranked list of players who best match that profile.

## Why This Is Useful

This feature makes the project more realistic and scouting-oriented. It does not rank players only by raw numbers. Instead, it evaluates how well each player fits a specific tactical or recruitment need.

This approach also connects data analysis with product thinking, because the final output is designed to support a decision-making process: identifying players with specific characteristics.

## Current Dataset Limitations

The current dataset does not include some important scouting variables, such as:

- Dominant foot
- Market value
- Salary
- Contract length
- Injury history
- Match-by-match performance
- Tactical role assigned by the coach

Because of that, the first version of this feature should focus only on statistical performance indicators available in the dataset.

## MVP Proposal

The first version of the Scouting Profile Finder could include:

- Position filter
- Metric selection
- Manual metric weights
- Per-90 metrics
- Position-based percentiles
- Final scouting fit score
- Ranked player table

A future version could include an interactive dashboard or app interface where users define the target profile and immediately see the best matching players.
