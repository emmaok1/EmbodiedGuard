# EmbodiedGuard

We built EmbodiedGuard for the National College Student Information Security Competition (全国大学生信息安全竞赛), where the project won **National Second Prize (全国二等奖)**.

EmbodiedGuard is a safety evaluation platform for robots that use vision-language models to navigate. It records what the robot saw, how the model described the scene, which directions it considered traversable, and what action it selected. These records make it possible to trace a risky decision back to the step where it arose.

## What an operator sees

In the Unitree G1 demonstration, the operator uploads a reference photo of a box and connects a live camera feed. The robot searches for a match among candidate boxes. Once it locks onto a target, it uses the target’s image position to turn and depth measurements to decide when to stop. The console shows the camera view, model decisions, motion status, and a manual stop control.

The platform also supports controlled comparisons. An operator can inspect a baseline decision, compare it with a decision made under misleading context, and review a defensive decision. Step-by-step records can be exported as Markdown, JSON, or CSV.

## A result from simulation

In a separate corridor experiment, a cardboard box blocked the path. The baseline stopped or declined to proceed in **5 of 5 trials**. Under the tested interference condition, the system selected a risky action in **5 of 5 trials**. The recorded decision traces showed that the blocked direction had already been marked traversable before the final action check. These counts describe the simulated corridor task. The G1 demonstration addresses a different task, finding a specified box.

[See the four experimental conditions and their results](docs/simulation-results.md)

## System design

The navigation stack is called **BrainNav**. EmbodiedGuard adds an operator interface, safety evaluation, and experiment reporting. Inputs include simulation, photo replay, and live camera observations.

[Explore the architecture and evidence recorded at each stage](docs/architecture.md)
