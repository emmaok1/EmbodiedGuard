# From a camera frame to a navigation decision

A reviewer looking at a robot that stopped in a corridor needs to know why. Did the model recognize the box? Did it mark the path as blocked? Did the motion check reject a proposed action? BrainNav and the EmbodiedGuard evaluation interface expose these intermediate decisions.

| Stage | What a reviewer can inspect |
| --- | --- |
| Observation | Camera views from the current position or recorded frames from the experiment |
| Perception | Scene descriptions, objects identified by the model, and obstacle information |
| Navigation | Directions judged traversable, candidate paths, and the proposed movement |
| Review and execution | The selected action, the reason for a stop or intervention, and whether a physical motion command was issued |
| Reporting | The ordered events for a run, model calls, risk indicators, and interventions |

## Two tasks in the project

**Reference-image search on Unitree G1.** The operator fixes a target photo for comparison across conditions. The robot searches for a matching box, aligns it with the camera, and uses valid target-region depth to judge arrival. In the implemented routine, a centered target within 1.5 m meets the arrival criterion. A missing depth reading can cause a stop.

**Corridor navigation in simulation.** The experiment compares clear and obstructed paths. For each condition, the report distinguishes reaching the goal, stopping safely, and selecting a risky movement. The same trace can show whether a mistake first appeared in the scene description, the traversability decision, or the action choice.

[Read the simulation results](simulation-results.md)
