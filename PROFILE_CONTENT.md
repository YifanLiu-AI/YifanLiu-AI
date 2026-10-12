<p>
  <img src="assets/header.svg?v=serif-3" alt="Yifan Liu — Embodied AI, Bimanual Manipulation, Dexterous Manipulation" width="900">
</p>

<p>
  <samp><a href="https://yifanliu-ai.github.io">website ↗</a> &nbsp; / &nbsp; <a href="https://wui.me/blog">research blog ↗</a> &nbsp; / &nbsp; <a href="mailto:yifanliu.ai@gmail.com">email ↗</a> &nbsp; / &nbsp; <a href="https://yifanliu-ai.github.io/assets/files/curriculum_vitae.pdf">English CV (PDF) ↗</a></samp>
</p>

<br>

<img src="assets/section-about.svg?v=serif-3" alt="About" width="900">

I'm a B.Eng. student in the **School of Mechanical and Automotive Engineering, South China University of Technology (SCUT)**, with an expected graduation date of **June 2028**.

My work focuses on robot learning, simulation-to-real workflows, and bimanual and dexterous manipulation. I build and evaluate policies, investigate task failures, and develop teleoperation and rollout-data pipelines.

<br>

<img src="assets/section-experience.svg?v=serif-3" alt="Research &amp; Internship Experience" width="900">

<img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/slai-logo-balanced.png" alt="SLAI" height="28"> &nbsp; **Shenzhen Loop Area Institute (SLAI) · RAPID Lab**

Research Assistant Intern &nbsp; · &nbsp; **June–September 2026**  
Advisor: Prof. Hui Cheng, School of Computer Science and Engineering, Sun Yat-sen University.

<img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/miaa-logo.webp" alt="MIAA Lab" height="28"> &nbsp; **South China University of Technology · MIAA Lab**

Undergraduate Research Student &nbsp; · &nbsp; **November 2025–May 2026**  
Advisor: Assoc. Prof. Huiping Zhuang, Shien-Ming Wu School of Intelligent Engineering.

<br>

<img src="assets/section-projects.svg?v=serif-3" alt="Selected Research Projects" width="900">

### NeurIPS 2026 RoboSyn Challenge
**August–October 2026 · Ongoing**  
Zepeng Lin, Yifan Liu, Wei Shan, Yinuo Ge, Muyang Li
[Challenge website](https://robosyn-bench.net/) · [Code (private)](https://github.com/innovationasuna/RoboSynChallenge_MIAA-HCC) · [Checkpoints](https://huggingface.co/innovationasuna/robosynchallenge-checkpoint)

- **Synthetic trajectory-driven bimanual manipulation**: The challenge provides 1,000 synthetic demonstrations for each of 10 tasks; the organizers introduce domain randomization during training and evaluation to reduce the sim-to-real gap.
- **Failure-stage diagnosis**: Trained π0.5 baselines across all 10 tasks using four H100 GPUs and an RTX 4090. Sparse rewards made failure stages difficult to identify; added rollout sensors and subtask checks to localize the main failures in low-success-rate tasks.
- **Mixer Operating**: Traced pressing failures through raw data, normalization, and control; found 195/1,000 demonstrations with action/state values outside the current joint limits. Removed incompatible demonstrations and applied ISR-based trajectory frame selection; under random seeds, success improved from **78.3% (47/60) to 93.3% (56/60)**.
- **Manipulate Pipette**: Used motion planning as the primary controller, with lateral residual corrections from online π0.5 predictions added to the downward plan to address insufficient pressing depth. In a paired evaluation on 60 frozen random development scenarios, success rate increased from **78.3% (47/60) to 96.7% (58/60)**.

### TwinPath Wrist
**June–September 2026 · ICRA 2027 submission, under review; second author**  
Haitao Jiang, Yifan Liu, Yanbin Chang, Wei Zhang, Xiaogang Xiong, Hui Cheng†
[Code](https://github.com/YifanLiu-AI/slai-manipulation)

- **End-to-end real-to-real infrastructure**: Independently built teleoperation, data collection, and π0.5/Diffusion Policy imitation-learning workflows from scratch for UR5e, a custom wrist, and different end effectors, using equipment shared by RAPID (Prof. Hui Cheng) and MMLab (Prof. Ping Luo). Supported four configurations—Wuji hand, custom wrist + Wuji hand, gripper, and custom wrist + gripper—for **fixed-versus-enabled wrist experiments**.
- **Teleoperation**: Used a SpaceMouse to control the 6-DoF UR5e, wuji-retargeting (the official adaptation of dex-retargeting) for the 20-DoF Wuji hand, and a custom master wrist built by a senior lab member for the 2-DoF follower wrist.
- **Data collection**: Frequent jumps in thumb–index distance during grasping prompted replacing real-time wuji-retargeting with keyboard-selected gesture presets, reducing control complexity and improving data stability. Integrated motion planning and saved key poses for rapid homing and preset-pose switching, reserving manual teleoperation for difficult subtasks. Built web-based visualization and hand-temperature alerts. Compared with the conventional SpaceMouse/dex-retargeting workflow, this process enabled inexperienced operators to collect **40+ successful demonstrations in 30 minutes**.
- **Imitation learning**: Investigated grasp misalignment and weak generalization during Wuji-hand picking. Disabled camera inputs one at a time and found that removing one view barely changed policy trajectories. Added training perturbations and random camera/state input dropout; the retrained policy completed the pick test task.

### ICRA 2026 LeHome Challenge
**November 2025–May 2026 · Ebtech-MIAA; final rank: #17**  

[Challenge website](https://lehome-challenge.com/)
[Code](https://github.com/YifanLiu-AI/lehome-challenge)

- **Bimanual garment folding**: Contributed rollout-data augmentation and policy tuning to the team's X-VLA imitation-learning pipeline. The **initial submission ranked 2nd globally**; the **final team rank was 17th**.
- **Baseline selection**: Trained and evaluated Diffusion Policy and X-VLA; selected X-VLA based on baseline success rates and compute requirements.
- **Closed-loop tuning**: Built an automated training, closed-loop evaluation, and configuration-adjustment pipeline after observing that lower loss could yield lower success. At 30k training steps and **60 evaluation episodes per setting**, augmentation limits of 0, 1, 2, and 3 yielded success rates of 76.67%, **86.67%**, 80%, and 78.33%, respectively. Selected one augmentation, improving long-sleeve success on training-set scenarios from **76.67% to 86.67%**.
- **Data flywheel**: The official dataset provides 25 demonstrations for each of 40 seen garments; limited data hindered generalization. Adding low-quality simulation demonstrations collected by human experts through master-arm teleoperation reduced success. Independently developed a multi-round RFT data flywheel that fed policy rollouts back into training. Under compute constraints, the team generated roughly 100 rollout trajectories, achieving success-rate gains of **20% on the training set and 2% on the test set**. The champion's post-competition report described similar components using tens of thousands of rollouts.
- **Trajectory filtering**: Clustered rollout episodes by completion time and reward to reduce redundant successful trajectories while retaining longer successes with corrective behavior.

<br>

<img src="assets/section-skills.svg?v=serif-3" alt="Technical Skills" width="900">

- **Simulation & Robot Learning:** Isaac Lab / Isaac Sim, π0.5, Diffusion Policy; SFT, RFT, data flywheels.
- **Real Robots:** Real-to-real, real-to-sim, SpaceMouse teleoperation & data collection, dex-retargeting.
- **Robot Platforms:** Manipulators: LeRobot SO-101, AgileX PiPER, UR5e; Dexterous Hand: Wuji Hand1.
- **Agent Collaboration:** Claude Code, Codex.

<br>

<img src="assets/section-education.svg?v=serif-3" alt="Education &amp; Honors" width="900">

<img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/scut-emblem.png" alt="SCUT" height="28"> &nbsp; **South China University of Technology**  
School of Mechanical and Automotive Engineering · B.Eng. candidate  
**September 2024–June 2028 (expected)**


- **2026.08:** National Safety Science and Engineering Practice Innovation Competition (Software Track), **National Third Prize** | Team Lead
- **2025.09:** “Shenzhen Cup” Mathematical Modeling Challenge, **Guangdong Region Third Prize** | Team Lead
- **2025.12:** National Undergraduate Mathematical Contest in Modeling, **Guangdong Merit Award** | Core Member
- **2026–present:** Computer Science Student Research Program (SRP) | Core Member
- **2026–present:** Undergraduate Innovation Training Project, **National-level project approval** | Core Member
- **2025–2026:** Undergraduate Innovation Training Project, **National-level project approval** | Core Member
