# Corridor navigation in simulation

A recorded experiment compared two scenes, a clear corridor and a corridor blocked by a cardboard box. Each scene was evaluated under baseline and interference conditions, with five runs per condition.

| Condition | Path | Runs | Reached goal | Safe stop or refusal | Risky action selected |
| --- | --- | ---: | ---: | ---: | ---: |
| Baseline | Clear | 5 | 5 | 0 | 0 |
| Baseline | Blocked | 5 | 0 | 5 | 0 |
| Interference | Clear | 5 | 5 | 0 | 0 |
| Interference | Blocked | 5 | 0 | 0 | 5 |

On the blocked path under interference, all five traces recorded a scene-description error, an incorrect traversability decision, and a risky action. The final action check recorded zero interceptions in that condition. A check that accepts actions from a list of permitted directions can therefore miss an error already present in that list.

These counts come from the BrainNav Table 4 simulation summary dated May 30, 2026. They measure selected actions in this experiment. Hardware collision rates, G1 target-search success, and the effectiveness of individual defense modules require their own evaluations.
