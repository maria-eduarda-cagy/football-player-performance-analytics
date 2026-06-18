# Data Dictionary

This document describes the columns available in the **2022–2023 Football Player Stats** dataset.

During the data cleaning phase, the original column names were renamed to a standardized `snake_case` format to improve readability and make the dataset easier to work with in Python.

## Key Columns and Metrics

Although the dataset contains 124 columns, some variables are especially important for this project because they support player comparison, feature engineering, per-90 analysis, and scouting-style insights.

### Player Identification

* `player`: player name
* `nation`: player nationality
* `position`: player position
* `squad`: club or team
* `competition`: competition or league
* `age`: player age

### Playing Time

Playing time is essential because raw totals can be misleading. Players with more minutes naturally have more opportunities to accumulate goals, assists, passes, tackles, and other actions.

* `minutes`: total minutes played
* `minutes_90s`: minutes played divided by 90
* `matches_played`: matches played
* `matches_started`: matches started

The `minutes_90s` column is especially important because it allows the creation of per-90 metrics, making player comparisons fairer.

### Offensive Metrics

* `goals`
* `assists`
* `shots`
* `shots_on_target`
* `shots_on_target_pct`
* `goals_per_shot`
* `goals_per_shot_on_target`

These metrics will be useful to identify finishers, high-volume shooters, and players with strong goal contribution.

### Passing and Progression Metrics

* `total_passes_completed`
* `total_passes_attempted`
* `total_pass_completion_pct`
* `progressive_pass_distance`
* `passes_into_final_third`
* `passes_into_penalty_area`
* `progressive_passes`

These metrics are important for identifying players who contribute to build-up play and ball progression.

### Chance Creation Metrics

* `shot_creating_actions`
* `goal_creating_actions`
* `assisted_shots`
* `sca_live_ball_passes`
* `sca_dribbles`
* `gca_live_ball_passes`

These metrics are useful for identifying creative players who generate attacking value beyond goals and assists.

### Defensive Metrics

* `tackles`
* `tackles_won`
* `interceptions`
* `blocks`
* `clearances`
* `tackles_plus_interceptions`
* `errors_leading_to_shot`

These metrics are useful for identifying defensive specialists and comparing defensive involvement across positions.

### Possession and Ball Progression Metrics

* `touches`
* `carries`
* `carry_progressive_distance`
* `progressive_carries`
* `carries_into_final_third`
* `carries_into_penalty_area`
* `passes_received`
* `progressive_passes_received`

These metrics are important for identifying players involved in possession, carrying, and progression.

### Aerial Duel Metrics

* `aerial_duels_won`
* `aerial_duels_lost`
* `aerial_duels_won_pct`

These metrics are especially useful when analyzing defenders, center backs, strikers, and other aerially involved roles.

## Planned Derived Metrics

The project will later create derived metrics such as:

* `goals_per_90`
* `assists_per_90`
* `goal_contribution_per_90`
* `shots_per_90`
* `passes_per_90`
* `progressive_passes_per_90`
* `defensive_actions_per_90`
* `progressive_carries_per_90`

These derived metrics will make the analysis fairer by adjusting performance to minutes played.

---

# Full Column Dictionary

| Original Column | Renamed Column                   | Description                                                                                                        |
| --------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `Rk`            | `rank`                           | Player ranking in the original dataset.                                                                            |
| `Player`        | `player`                         | Player's name.                                                                                                     |
| `Nation`        | `nation`                         | Player's nationality.                                                                                              |
| `Pos`           | `position`                       | Player's position.                                                                                                 |
| `Squad`         | `squad`                          | Player's squad or club name.                                                                                       |
| `Comp`          | `competition`                    | Competition or league in which the squad plays.                                                                    |
| `Age`           | `age`                            | Player's age.                                                                                                      |
| `Born`          | `birth_year`                     | Player's year of birth.                                                                                            |
| `MP`            | `matches_played`                 | Matches played.                                                                                                    |
| `Starts`        | `matches_started`                | Matches started.                                                                                                   |
| `Min`           | `minutes`                        | Minutes played.                                                                                                    |
| `90s`           | `minutes_90s`                    | Minutes played divided by 90.                                                                                      |
| `Goals`         | `goals`                          | Goals scored.                                                                                                      |
| `Shots`         | `shots`                          | Total shots, excluding penalty kicks.                                                                              |
| `SoT`           | `shots_on_target`                | Shots on target, excluding penalty kicks.                                                                          |
| `SoT%`          | `shots_on_target_pct`            | Percentage of shots on target, excluding penalty kicks.                                                            |
| `G/Sh`          | `goals_per_shot`                 | Goals per shot.                                                                                                    |
| `G/SoT`         | `goals_per_shot_on_target`       | Goals per shot on target, excluding penalty kicks.                                                                 |
| `ShoDist`       | `average_shot_distance`          | Average shot distance from goal, in yards, excluding penalty kicks.                                                |
| `ShoFK`         | `free_kick_shots`                | Shots from free kicks.                                                                                             |
| `ShoPK`         | `penalty_kicks_scored`           | Penalty kicks scored.                                                                                              |
| `PKatt`         | `penalty_kicks_attempted`        | Penalty kicks attempted.                                                                                           |
| `PasTotCmp`     | `total_passes_completed`         | Total passes completed.                                                                                            |
| `PasTotAtt`     | `total_passes_attempted`         | Total passes attempted.                                                                                            |
| `PasTotCmp%`    | `total_pass_completion_pct`      | Total pass completion percentage.                                                                                  |
| `PasTotDist`    | `total_pass_distance`            | Total distance, in yards, that completed passes traveled in any direction.                                         |
| `PasTotPrgDist` | `progressive_pass_distance`      | Total distance, in yards, that completed passes traveled toward the opponent's goal.                               |
| `PasShoCmp`     | `short_passes_completed`         | Short passes completed, between 5 and 15 yards.                                                                    |
| `PasShoAtt`     | `short_passes_attempted`         | Short passes attempted, between 5 and 15 yards.                                                                    |
| `PasShoCmp%`    | `short_pass_completion_pct`      | Short pass completion percentage, between 5 and 15 yards.                                                          |
| `PasMedCmp`     | `medium_passes_completed`        | Medium passes completed, between 15 and 30 yards.                                                                  |
| `PasMedAtt`     | `medium_passes_attempted`        | Medium passes attempted, between 15 and 30 yards.                                                                  |
| `PasMedCmp%`    | `medium_pass_completion_pct`     | Medium pass completion percentage, between 15 and 30 yards.                                                        |
| `PasLonCmp`     | `long_passes_completed`          | Long passes completed, longer than 30 yards.                                                                       |
| `PasLonAtt`     | `long_passes_attempted`          | Long passes attempted, longer than 30 yards.                                                                       |
| `PasLonCmp%`    | `long_pass_completion_pct`       | Long pass completion percentage, longer than 30 yards.                                                             |
| `Assists`       | `assists`                        | Assists.                                                                                                           |
| `PasAss`        | `assisted_shots`                 | Passes that directly lead to a shot attempt.                                                                       |
| `Pas3rd`        | `passes_into_final_third`        | Completed passes that enter the final third of the pitch.                                                          |
| `PPA`           | `passes_into_penalty_area`       | Completed passes into the 18-yard box.                                                                             |
| `CrsPA`         | `crosses_into_penalty_area`      | Completed crosses into the 18-yard box.                                                                            |
| `PasProg`       | `progressive_passes`             | Progressive completed passes that move the ball toward the opponent's goal or into the penalty area.               |
| `PasAtt`        | `passes_attempted`               | Passes attempted.                                                                                                  |
| `PasLive`       | `live_ball_passes`               | Live-ball passes.                                                                                                  |
| `PasDead`       | `dead_ball_passes`               | Dead-ball passes.                                                                                                  |
| `PasFK`         | `free_kick_passes`               | Passes attempted from free kicks.                                                                                  |
| `TB`            | `through_balls`                  | Through balls completed between defenders into open space.                                                         |
| `Sw`            | `switches`                       | Switches of play traveling more than 40 yards across the width of the pitch.                                       |
| `PasCrs`        | `pass_crosses`                   | Crosses attempted as passes.                                                                                       |
| `TI`            | `throw_ins`                      | Throw-ins taken.                                                                                                   |
| `CK`            | `corner_kicks`                   | Corner kicks taken.                                                                                                |
| `CkIn`          | `inswinging_corners`             | Inswinging corner kicks.                                                                                           |
| `CkOut`         | `outswinging_corners`            | Outswinging corner kicks.                                                                                          |
| `CkStr`         | `straight_corners`               | Straight corner kicks.                                                                                             |
| `PasCmp`        | `passes_completed`               | Passes completed.                                                                                                  |
| `PasOff`        | `pass_offsides`                  | Offsides from passes.                                                                                              |
| `PasBlocks`     | `passes_blocked`                 | Passes blocked by an opponent standing in the path.                                                                |
| `SCA`           | `shot_creating_actions`          | Shot-creating actions.                                                                                             |
| `ScaPassLive`   | `sca_live_ball_passes`           | Completed live-ball passes that lead to a shot attempt.                                                            |
| `ScaPassDead`   | `sca_dead_ball_passes`           | Completed dead-ball passes that lead to a shot attempt.                                                            |
| `ScaDrib`       | `sca_dribbles`                   | Successful dribbles that lead to a shot attempt.                                                                   |
| `ScaSh`         | `sca_shots`                      | Shots that lead to another shot attempt.                                                                           |
| `ScaFld`        | `sca_fouls_drawn`                | Fouls drawn that lead to a shot attempt.                                                                           |
| `ScaDef`        | `sca_defensive_actions`          | Defensive actions that lead to a shot attempt.                                                                     |
| `GCA`           | `goal_creating_actions`          | Goal-creating actions.                                                                                             |
| `GcaPassLive`   | `gca_live_ball_passes`           | Completed live-ball passes that lead to a goal.                                                                    |
| `GcaPassDead`   | `gca_dead_ball_passes`           | Completed dead-ball passes that lead to a goal.                                                                    |
| `GcaDrib`       | `gca_dribbles`                   | Successful dribbles that lead to a goal.                                                                           |
| `GcaSh`         | `gca_shots`                      | Shots that lead to another goal-scoring shot.                                                                      |
| `GcaFld`        | `gca_fouls_drawn`                | Fouls drawn that lead to a goal.                                                                                   |
| `GcaDef`        | `gca_defensive_actions`          | Defensive actions that lead to a goal.                                                                             |
| `Tkl`           | `tackles`                        | Number of players tackled.                                                                                         |
| `TklWon`        | `tackles_won`                    | Tackles in which the tackler's team won possession of the ball.                                                    |
| `TklDef3rd`     | `tackles_defensive_third`        | Tackles in the defensive third.                                                                                    |
| `TklMid3rd`     | `tackles_middle_third`           | Tackles in the middle third.                                                                                       |
| `TklAtt3rd`     | `tackles_attacking_third`        | Tackles in the attacking third.                                                                                    |
| `TklDri`        | `dribblers_tackled`              | Number of dribblers tackled.                                                                                       |
| `TklDriAtt`     | `dribbler_tackle_attempts`       | Number of times dribbled past plus number of tackles.                                                              |
| `TklDri%`       | `dribblers_tackled_pct`          | Percentage of dribblers tackled.                                                                                   |
| `TklDriPast`    | `times_dribbled_past`            | Number of times dribbled past by an opposing player.                                                               |
| `Blocks`        | `blocks`                         | Number of times blocking the ball by standing in its path.                                                         |
| `BlkSh`         | `shots_blocked`                  | Number of times blocking a shot by standing in its path.                                                           |
| `BlkPass`       | `passes_blocked_defensive`       | Number of times blocking a pass by standing in its path.                                                           |
| `Int`           | `interceptions`                  | Interceptions.                                                                                                     |
| `Tkl+Int`       | `tackles_plus_interceptions`     | Number of tackles plus interceptions.                                                                              |
| `Clr`           | `clearances`                     | Clearances.                                                                                                        |
| `Err`           | `errors_leading_to_shot`         | Mistakes leading to an opponent's shot.                                                                            |
| `Touches`       | `touches`                        | Number of times a player touched the ball. Receiving, dribbling, and passing in one sequence counts as one touch.  |
| `TouDefPen`     | `touches_defensive_penalty_area` | Touches in the defensive penalty area.                                                                             |
| `TouDef3rd`     | `touches_defensive_third`        | Touches in the defensive third.                                                                                    |
| `TouMid3rd`     | `touches_middle_third`           | Touches in the middle third.                                                                                       |
| `TouAtt3rd`     | `touches_attacking_third`        | Touches in the attacking third.                                                                                    |
| `TouAttPen`     | `touches_attacking_penalty_area` | Touches in the attacking penalty area.                                                                             |
| `TouLive`       | `live_ball_touches`              | Live-ball touches, excluding corners, free kicks, throw-ins, kick-offs, goal kicks, and penalty kicks.             |
| `ToAtt`         | `take_ons_attempted`             | Number of attempts to take on defenders while dribbling.                                                           |
| `ToSuc`         | `successful_take_ons`            | Number of defenders successfully taken on by dribbling past them.                                                  |
| `ToSuc%`        | `take_on_success_pct`            | Percentage of take-ons completed successfully.                                                                     |
| `ToTkl`         | `take_ons_tackled`               | Number of times tackled by a defender during a take-on attempt.                                                    |
| `ToTkl%`        | `take_ons_tackled_pct`           | Percentage of times tackled by a defender during a take-on attempt.                                                |
| `Carries`       | `carries`                        | Number of times the player controlled the ball with their feet.                                                    |
| `CarTotDist`    | `carry_total_distance`           | Total distance, in yards, a player moved the ball while controlling it with their feet in any direction.           |
| `CarPrgDist`    | `carry_progressive_distance`     | Total distance, in yards, a player moved the ball while controlling it with their feet toward the opponent's goal. |
| `CarProg`       | `progressive_carries`            | Progressive carries that move the ball toward the opponent's goal or into the penalty area.                        |
| `Car3rd`        | `carries_into_final_third`       | Carries that enter the final third of the pitch.                                                                   |
| `CPA`           | `carries_into_penalty_area`      | Carries into the 18-yard box.                                                                                      |
| `CarMis`        | `carries_miscontrolled`          | Number of times a player failed when attempting to gain control of the ball.                                       |
| `CarDis`        | `carries_dispossessed`           | Number of times a player lost control of the ball after being tackled by an opponent.                              |
| `Rec`           | `passes_received`                | Number of times a player successfully received a pass.                                                             |
| `RecProg`       | `progressive_passes_received`    | Progressive passes received.                                                                                       |
| `CrdY`          | `yellow_cards`                   | Yellow cards.                                                                                                      |
| `CrdR`          | `red_cards`                      | Red cards.                                                                                                         |
| `2CrdY`         | `second_yellow_cards`            | Second yellow cards.                                                                                               |
| `Fls`           | `fouls_committed`                | Fouls committed.                                                                                                   |
| `Fld`           | `fouls_drawn`                    | Fouls drawn.                                                                                                       |
| `Off`           | `offsides`                       | Offsides.                                                                                                          |
| `Crs`           | `crosses`                        | Crosses.                                                                                                           |
| `TklW`          | `tackles_won_misc`               | Tackles in which the tackler's team won possession of the ball.                                                    |
| `PKwon`         | `penalty_kicks_won`              | Penalty kicks won.                                                                                                 |
| `PKcon`         | `penalty_kicks_conceded`         | Penalty kicks conceded.                                                                                            |
| `OG`            | `own_goals`                      | Own goals.                                                                                                         |
| `Recov`         | `loose_balls_recovered`          | Number of loose balls recovered.                                                                                   |
| `AerWon`        | `aerial_duels_won`               | Aerial duels won.                                                                                                  |
| `AerLost`       | `aerial_duels_lost`              | Aerial duels lost.                                                                                                 |
| `AerWon%`       | `aerial_duels_won_pct`           | Percentage of aerial duels won.                                                                                    |

## Notes

* The dataset is aggregated at player-season level.
* The dataset is useful for comparing players, positions, squads, and competitions.
* The original raw dataset keeps the original column names.
* The cleaned dataset uses standardized `snake_case` column names.
* For fairer player comparisons, many raw totals should later be normalized using `minutes_90s`.
* This dictionary should be updated if new derived metrics are created during the feature engineering phase.
