<p>
  <img src="assets/header.svg?v=serif-3" alt="Yifan Liu — Embodied AI, Bimanual Manipulation, Dexterous Manipulation" width="900">
</p>

<p>
  <samp><a href="https://yifanliu-ai.github.io">website ↗</a> &nbsp; / &nbsp; <a href="https://wui.me/blog">research blog ↗</a> &nbsp; / &nbsp; <a href="mailto:yifanliu.ai@gmail.com">email ↗</a></samp>
</p>

<br>

<img src="assets/section-about.svg?v=serif-3" alt="About" width="900">

I'm a B.Eng. student in the **School of Mechanical and Automotive Engineering, South China University of Technology (SCUT)**, with an expected graduation date of **June 2028**.

My work focuses on robot learning, simulation-to-real workflows, and bimanual and dexterous manipulation. I build and evaluate policies, investigate task failures, and develop teleoperation and rollout-data pipelines.

<br>

<img src="assets/section-experience.svg?v=serif-3" alt="Research &amp; Internship Experience" width="900">

<img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/slai-logo-balanced.png" alt="SLAI" height="28"> &nbsp; **Shenzhen Loop Area Institute (SLAI) · RAPID Lab**

Research Assistant Intern &nbsp; · &nbsp; **June–September 2026**  
Advisor: Prof. Hui Cheng, Sun Yat-sen University.

<img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/miaa-logo.webp" alt="MIAA Lab" height="28"> &nbsp; **South China University of Technology · MIAA Lab**

Student &nbsp; · &nbsp; **November 2025–May 2026**  
Advisor: Assoc. Prof. Huiping Zhuang, Shien-Ming Wu School of Intelligent Engineering.

<br>

<img src="assets/section-projects.svg?v=serif-3" alt="Selected Research Projects" width="900">

### <img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/neurips-logo.webp" alt="NeurIPS" height="28"> &nbsp; NeurIPS 2026 RoboSyn Challenge
**August–October 2026 · Competition in progress**  
Zepeng Lin, **Yifan Liu**, Wei Shan, Yinuo Ge, Muyang Li  
[Challenge website](https://robosyn-bench.net/)

- **Synthetic trajectory-driven bimanual manipulation challenge:** The challenge provides 1,000 synthetic demonstrations for each of 10 tasks; the organizers use domain randomization during training and evaluation to reduce the sim-to-real gap.
- **Failure analysis for low-success-rate tasks:** Trained baseline π0.5 policies for all 10 tasks using four H100 GPUs and an RTX 4090. Sparse rewards made failure stages difficult to identify; added sensors and subtask checks during rollout to localize the main failure causes.
- **Mixer Operating:** Investigated press failures and found that action/state values in 195 of the 1,000 official demonstrations exceeded the current joint limits. Checked the raw data, normalization, and control pipeline, removed incompatible demonstrations, and introduced ISR-based frame selection to compress bimanual trajectories, reducing **training sampling points by approximately 77%**. Success rate increased from **83% to 93%**.
- **Item Assembly:** Motion after grasping takes place in obstacle-free space, but the policy alone did not achieve 100% success in docking, motivating the use of a conventional planner. Extracted waypoints from successful episodes and used the planner to follow them after the policy grasped and reoriented both objects. In an initial test on 20 seeds, success rate increased from **5% to 75%**.
- **Manipulate Pipette:** added a downward waypoint correction for insufficient press stroke; evaluation on 20 fixed scenarios improved success rate from **75% to 90%**.

### <img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/icra27-logo.webp" alt="ICRA 2027" height="28"> &nbsp; ICRA 2027 · TwinPath Wrist
**June–September 2026 · Second author · Under review**  
Haitao Jiang, **Yifan Liu**, Yanbin Chang, Wei Zhang, Xiaogang Xiong, Hui Cheng†

- **End-to-end real2real infrastructure:** Using lab equipment shared by Prof. Hui Cheng (RAPID) and Prof. Ping Luo (MMLab), independently built teleoperation, data collection, and imitation-learning workflows (π0.5 and Diffusion Policy) from scratch for UR5e, a custom wrist, and different end effectors. Covered four configurations: wuji-hand, custom wrist + wuji-hand, gripper, and custom wrist + gripper, and built infrastructure for **fixed-versus-enabled wrist comparisons**.
- **Teleoperation:** Controlled a 6-DoF UR5e arm with a SpaceMouse, a 20-DoF wuji-hand with wuji-retargeting (an official adaptation based on dex-retargeting), and a 2-DoF follower wrist with a custom master wrist built by a senior lab member.
- **Data collection:** Frequent jumps in thumb–index distance during grasping led to discontinuing real-time wuji-retargeting. Stored common gestures for keyboard control to reduce operational degrees of freedom and improve data stability. Integrated motion planning into the collection workflow: saved key poses for rapid homing and preset-pose switching, and reserved manual teleoperation for difficult subtasks. Built a visualization webpage and wuji-hand temperature alerts. Compared with the previous SpaceMouse and dex-retargeting workflow, the streamlined process enabled inexperienced operators to collect **over 40 successful demonstrations within half an hour**.
- **Imitation learning:** During testing, observed grasp misalignment and weak generalization in the wuji-hand pick phase. Disabled camera inputs one at a time; disabling one view did not noticeably change the policy trajectory. Added training perturbations and randomly dropped camera and state inputs; the retrained policy completed the pick test task.

### <img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/icra26-logo.webp" alt="ICRA 2026" height="28"> &nbsp; ICRA 2026 LeHome Challenge
**November 2025–May 2026 · Ebtech-MIAA**  
**Initial submission: global #2 · Final rank: global #17**  
[Challenge website](https://lehome-challenge.com/) · [Code](https://github.com/YifanLiu-AI/lehome-challenge)

- **Bimanual deformable-garment folding challenge:** The team used X-VLA-based imitation learning; my main contribution was tuning through rollout-data injection. The **initial submission ranked 2nd globally**, while the **final ranking was 17th**.
- **Baseline selection:** Trained and evaluated policies including Diffusion Policy and X-VLA, then selected X-VLA as the primary tuning target based on available compute and baseline success rates.
- **Hyperparameter-tuning pipeline:** Observed that checkpoints with lower loss could have lower closed-loop success rates. Built an automated training, closed-loop evaluation, and configuration-adjustment pipeline, selecting configurations by closed-loop success rate. In an augmentation ablation at 30k steps with 60 episodes per configuration, `max_num_transforms=0/1/2/3` yielded 76.67%/**86.67%**/80%/78.33%; selected one augmentation. Training-set success rate on the long-sleeve task increased from **76.67% to 86.67%**.
- **Data flywheel:** The official dataset contained 40 seen garments with 25 demonstrations each; limited data hindered policy generalization. Adding lower-quality simulation demonstrations collected by human experts through master-arm teleoperation reduced success rate. I independently developed a multi-round RFT data flywheel that injected rollout trajectories into training. With limited compute, we generated about 100 rollout trajectories and observed success-rate improvements of **20% on the training set and 2% on the test set**. The champion's post-competition report described similar components with tens of thousands of rollout trajectories.
- **Rollout-data filtering:** Clustered episodes by completion time and reward to reduce repeated injection of successful trajectories, while retaining longer successful trajectories containing corrections as an initial dataset-filtering step.

<br>

<img src="assets/section-skills.svg?v=serif-3" alt="Technical Skills" width="900">

- **Simulation & learning** — Isaac Lab / Isaac Sim · π0.5 · Diffusion Policy · SFT · RFT · Data Flywheel
- **Real-robot workflows** — Real-to-Real · Real-to-Sim · SpaceMouse Teleoperation & Data Collection · dex-retargeting
- **Robot platforms** — LeRobot SO-101 · AgileX PiPER · UR5e · Wuji Hand1
- **Agent collaboration** — Claude Code · Codex

<br>

<img src="assets/section-education.svg?v=serif-3" alt="Education &amp; Honors" width="900">

<img src="https://raw.githubusercontent.com/YifanLiu-AI/wui-homepage/main/assets/img/scut-emblem.png" alt="SCUT" height="28"> &nbsp; **South China University of Technology**  
School of Mechanical and Automotive Engineering · B.Eng. in progress  
**September 2024–June 2028 (expected) · GPA: 3.17/4.00**

Core courses: Linear Algebra, Calculus, Probability Theory, Python Programming, Mechanical Principles and Design Fundamentals.

- **2026:** **National Third Prize**, National Safety Science and Engineering Practice Innovation Competition, Software Track — Team Lead.
- **2025:** **Guangdong Region Third Prize**, Shenzhen Cup Mathematical Modeling Challenge — Team Lead.
- **2025:** **Guangdong Merit Award**, National Undergraduate Mathematical Contest in Modeling — Core Member.
- **2026:** Computer Science Student Research Program (SRP) — Core Member.
- **2026:** Undergraduate Innovation Training Project — **National-level project approval**, Core Member.
- **2025–2026:** Undergraduate Innovation Training Project — **National-level project approval**, Core Member.
