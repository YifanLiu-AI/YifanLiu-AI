<p><img src="assets/header-compact.svg" alt="Yifan Liu — Robot learning and manipulation" width="900"></p>

<p><a href="https://wui.me"><img src="assets/serif-compact/link-website.svg" alt="wui.me" height="20"></a> &nbsp; <a href="https://wui.me/blog"><img src="assets/serif-compact/link-blog.svg" alt="Research blog" height="20"></a> &nbsp; <a href="mailto:shiyi20060618@gmail.com"><img src="assets/serif-compact/link-email.svg" alt="Email" height="20"></a></p>

<div>
<img src="assets/section-about-compact.svg" alt="About" width="900"><br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/about-mobile.svg"><img src="assets/serif-compact/about.svg" alt="I&#x27;m a B.Eng. student in the School of Mechanical and Automotive Engineering, South China University of Technology (SCUT), with an expected graduation date of June 2028. My work focuses on robot learning, simulation-to-real workflows, and bimanual and dexterous manipulation. I build and evaluate policies, investigate task failures, and develop teleoperation and rollout-data pipelines." width="900"></picture>
<br>
</div>
<br>

<div>
<img src="assets/section-experience-compact.svg" alt="Experience" width="900"><br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/slai-mobile.svg"><img src="assets/serif-compact/slai.svg" alt="Shenzhen Loop Area Institute (SLAI) · RAPID Lab Research Assistant Intern   ·   June–September 2026 Advisor: Prof. Hui Cheng, Sun Yat-sen University." width="900"></picture>
<br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/miaa-mobile.svg"><img src="assets/serif-compact/miaa.svg" alt="South China University of Technology · MIAA Lab Student   ·   November 2025–May 2026 Advisor: Assoc. Prof. Huiping Zhuang, Shien-Ming Wu School of Intelligent Engineering." width="900"></picture>
<br>
</div>
<br>

<div>
<img src="assets/section-projects-compact.svg" alt="Projects" width="900"><br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/robosyn-mobile.svg"><img src="assets/serif-compact/robosyn.svg" alt="NeurIPS 2026 RoboSyn Challenge August–October 2026 · Competition in progress Zepeng Lin, Yifan Liu, Wei Shan, Yinuo Ge, Muyang Li Trained π0.5 baselines for 10 bimanual tasks using four H100 GPUs and an RTX 4090; added sensors and subtask checks to diagnose low-success-rate tasks. Mixer Operating: traced press failures through raw demonstrations, normalization, and control. Removed 195 of 1,000 demonstrations incompatible with current joint limits and applied ISR-based bimanual frame selection, reducing training sampling points by about 77%. Historical optimization improved success rate from 83% to 93%; this is not an isolated ISR ablation. Item Assembly: let a planner take over after both objects were securely grasped, lifted, and aligned. Mapped object-space waypoints to end-effector targets using the current grasp transforms. In an initial comparison on 20 common scenarios, success increased from 1/20 to 15/20. Manipulate Pipette: added a downward waypoint correction for insufficient press stroke; evaluation on 20 fixed scenarios improved success rate from 75% to 90%." width="900"></picture>
<br>
<a href="https://robosyn-bench.net/"><img src="assets/serif-compact/link-robosyn-0.svg" alt="Challenge website" height="20"></a><br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/wrist-mobile.svg"><img src="assets/serif-compact/wrist.svg" alt="ICRA 2027 · TwinPath Wrist June–September 2026 · Second author · Under review Haitao Jiang, Yifan Liu, Yanbin Chang, Wei Zhang, Xiaogang Xiong, Hui Cheng† Independently built the teleoperation, data-collection, and imitation-learning workflows for UR5e, a custom wrist, and four end-effector configurations, supporting fixed-versus-enabled wrist comparisons. Integrated SpaceMouse control of UR5e, wuji-retargeting for the dexterous hand, and a senior lab member&#x27;s custom master wrist for the follower wrist. Combined stored hand gestures, keyboard control, saved key poses, and motion planning; reserved manual teleoperation for difficult subtasks. Added visualization and hand-temperature alerts. Inexperienced operators could collect over 40 successful demonstrations within half an hour. Tested camera inputs individually, then added perturbations and camera/state dropout during training; the retrained policy completed the pick test task." width="900"></picture>
<br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/lehome-mobile.svg"><img src="assets/serif-compact/lehome.svg" alt="ICRA 2026 LeHome Challenge November 2025–May 2026 · Ebtech-MIAA Initial submission: global #2 · Final rank: global #17 Trained and evaluated policies including Diffusion Policy and X-VLA, selecting X-VLA based on compute cost and baseline success rates. Built an automated training/evaluation pipeline driven by closed-loop success rate, rather than training loss alone. At 30k steps and 60 evaluation episodes per configuration, max_num_transforms=0/1/2/3 yielded 76.67% / 86.67% / 80.00% / 78.33%. Independently developed a multi-round RFT data flywheel for saving successful rollouts, filtering trajectories, merging datasets, and retraining. With about 100 rollout trajectories, observed success-rate gains of 20% on the training set and 2% on the test set. Clustered successful episodes by completion time and reward to reduce duplicate data injection while retaining longer trajectories containing corrections." width="900"></picture>
<br>
<a href="https://lehome-challenge.com/"><img src="assets/serif-compact/link-lehome-0.svg" alt="Challenge website" height="20"></a> &nbsp; <a href="https://github.com/sudo-yf/lehome-challenge"><img src="assets/serif-compact/link-lehome-1.svg" alt="Code" height="20"></a><br>
</div>
<br>

<div>
<img src="assets/section-skills-compact.svg" alt="Skills" width="900"><br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/skills-mobile.svg"><img src="assets/serif-compact/skills.svg" alt="Simulation &amp; learning — Isaac Lab / Isaac Sim · π0.5 · Diffusion Policy · SFT · RFT · Data Flywheel Real-robot workflows — Real-to-Real · Real-to-Sim · SpaceMouse Teleoperation &amp; Data Collection · dex-retargeting Robot platforms — LeRobot SO-101 · AgileX PiPER · UR5e · Wuji Hand1 Agent collaboration — Claude Code · Codex" width="900"></picture>
<br>
</div>
<br>

<div>
<img src="assets/section-education-compact.svg" alt="Education" width="900"><br>
<picture><source media="(max-width: 600px)" srcset="https://raw.githubusercontent.com/sudo-yf/sudo-yf/main/assets/serif-compact/education-mobile.svg"><img src="assets/serif-compact/education.svg" alt="South China University of Technology School of Mechanical and Automotive Engineering · B.Eng. in progress September 2024–June 2028 (expected) · GPA: 3.17/4.00 Core courses: Linear Algebra, Calculus, Probability Theory, Python Programming, Mechanical Principles and Design Fundamentals. 2026: National Third Prize, National Safety Science and Engineering Practice Innovation Competition, Software Track — Team Lead. 2025: Guangdong Region Third Prize, Shenzhen Cup Mathematical Modeling Challenge — Team Lead. 2025: Guangdong Merit Award, National Undergraduate Mathematical Contest in Modeling — Core Member. 2026: Computer Science Student Research Program (SRP) — Core Member. 2026: Undergraduate Innovation Training Project — National-level project approval, Core Member. 2025–2026: Undergraduate Innovation Training Project — National-level project approval, Core Member." width="900"></picture>
<br>
</div>
<br>

<a href="https://github.com/sudo-yf/sudo-yf/blob/main/PROFILE_CONTENT.md"><img src="assets/serif-compact/link-text-version.svg" alt="Text version" height="20"></a>
