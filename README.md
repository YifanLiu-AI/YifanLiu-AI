<h1 align="center">Yifan Liu</h1>

<p align="center">
  Undergraduate at South China University of Technology<br>
  <b>Embodied AI · Bimanual Manipulation · Dexterous Manipulation</b>
</p>

<p align="center">
  <a href="https://wui.me">Website</a> ·
  <a href="https://wui.me/blog">Blog</a> ·
  <a href="mailto:shiyi20060618@gmail.com">Email</a>
</p>

## About

I'm a B.Eng. student in the **School of Mechanical and Automotive Engineering, South China University of Technology (SCUT)**, with an expected graduation date of **June 2028**.

My work focuses on robot learning, simulation-to-real workflows, and bimanual and dexterous manipulation. I build and evaluate policies, investigate task failures, and develop teleoperation and rollout-data pipelines.

## Research and Internship Experience

- **Shenzhen Loop Area Institute (SLAI) · RAPID Lab** — Research Assistant Intern, **June–September 2026**  
  Advisor: Prof. Hui Cheng, Sun Yat-sen University.
- **South China University of Technology · MIAA Lab** — Student, **November 2025–May 2026**  
  Advisor: Assoc. Prof. Huiping Zhuang, Shien-Ming Wu School of Intelligent Engineering.

## Selected Research Projects

### NeurIPS 2026 RoboSyn Challenge
**August–October 2026 · Competition in progress**  
Zepeng Lin, **Yifan Liu**, Wei Shan, Yinuo Ge, Muyang Li  
[Challenge website](https://robosyn-bench.net/)

- Trained π0.5 baselines for 10 bimanual tasks using four H100 GPUs and an RTX 4090; added sensors and subtask checks to diagnose low-success-rate tasks.
- **Mixer Operating:** traced press failures through raw demonstrations, normalization, and control. Removed 195 of 1,000 demonstrations incompatible with current joint limits and applied ISR-based bimanual frame selection, reducing training sampling points by **about 77%**. Historical optimization improved success rate from **83% to 93%**; this is not an isolated ISR ablation.
- **Item Assembly:** let a planner take over after both objects were securely grasped, lifted, and aligned. Mapped object-space waypoints to end-effector targets using the current grasp transforms. In an initial comparison on 20 common scenarios, success increased from **1/20 to 15/20**.
- **Manipulate Pipette:** added a downward waypoint correction for insufficient press stroke; evaluation on 20 fixed scenarios improved success rate from **75% to 90%**.

### ICRA 2027 · TwinPath Wrist
**June–September 2026 · Second author · Under review**  
Haitao Jiang, **Yifan Liu**, Yanbin Chang, Wei Zhang, Xiaogang Xiong, Hui Cheng†

- Independently built the teleoperation, data-collection, and imitation-learning workflows for UR5e, a custom wrist, and four end-effector configurations, supporting fixed-versus-enabled wrist comparisons.
- Integrated SpaceMouse control of UR5e, wuji-retargeting for the dexterous hand, and a senior lab member's custom master wrist for the follower wrist.
- Combined stored hand gestures, keyboard control, saved key poses, and motion planning; reserved manual teleoperation for difficult subtasks. Added visualization and hand-temperature alerts. Inexperienced operators could collect **over 40 successful demonstrations within half an hour**.
- Tested camera inputs individually, then added perturbations and camera/state dropout during training; the retrained policy completed the pick test task.

### ICRA 2026 LeHome Challenge
**November 2025–May 2026 · Ebtech-MIAA**  
**Initial submission: global #2 · Final rank: global #17**  
[Challenge website](https://lehome-challenge.com/) · [Code](https://github.com/sudo-yf/lehome-challenge)

- Trained and evaluated policies including Diffusion Policy and X-VLA, selecting X-VLA based on compute cost and baseline success rates.
- Built an automated training/evaluation pipeline driven by **closed-loop success rate**, rather than training loss alone. At 30k steps and 60 evaluation episodes per configuration, `max_num_transforms=0/1/2/3` yielded **76.67% / 86.67% / 80.00% / 78.33%**.
- Independently developed a multi-round RFT data flywheel for saving successful rollouts, filtering trajectories, merging datasets, and retraining. With about 100 rollout trajectories, observed success-rate gains of **20% on the training set and 2% on the test set**.
- Clustered successful episodes by completion time and reward to reduce duplicate data injection while retaining longer trajectories containing corrections.

## Technical Skills

| Area | Tools and experience |
| :--- | :--- |
| Simulation & learning | Isaac Lab / Isaac Sim · π0.5 · Diffusion Policy · SFT · RFT · Data Flywheel |
| Real-robot workflows | Real-to-Real · Real-to-Sim · SpaceMouse Teleoperation & Data Collection · dex-retargeting |
| Robot platforms | LeRobot SO-101 · AgileX PiPER · UR5e · Wuji Hand1 |
| Agent collaboration | Claude Code · Codex |

## Education & Honors

**South China University of Technology**  
School of Mechanical and Automotive Engineering · B.Eng. in progress  
**September 2024–June 2028 (expected) · GPA: 3.17/4.00**

Core courses: Linear Algebra, Calculus, Probability Theory, Python Programming, Mechanical Principles and Design Fundamentals.

- **2026:** National Third Prize, National Safety Science and Engineering Practice Innovation Competition, Software Track — Team Lead.
- **2025:** Guangdong Region Third Prize, Shenzhen Cup Mathematical Modeling Challenge — Team Lead.
- **2025:** Guangdong Merit Award, National Undergraduate Mathematical Contest in Modeling — Core Member.
- **2026:** Computer Science Student Research Program (SRP) — Core Member.
- **2026:** Undergraduate Innovation Training Project — **National-level project approval**, Core Member.
- **2025–2026:** Undergraduate Innovation Training Project — **National-level project approval**, Core Member.

## Other Projects

<img align="right" width="180" src="https://chiikawa.r2.1591420.xyz/images/default/04.gif" alt="Chiikawa animation" />

<details>
        <summary>
          <b><a href="https://github.com/sudo-yf/DeepLabV3Plus">Weak-Boundary Smoke Semantic Segmentation</a></b><br>
          <sub>Fire-safety vision · smoke datasets · DeepLabV3+</sub>
        </summary>
        <br>
        <p>Semantic segmentation for smoke with weak boundaries, smoke-cloud confusion, and complex fire-safety scenes.</p>
        <ul>
          <li>Conducted more than ten smoke-burning experiments and collected over one hundred real smoke samples.</li>
          <li>Used SAM 3 for semi-automatic annotation and supplemented the dataset with 90 generated multi-scene smoke images.</li>
          <li>Collected and standardized <b>9,124 smoke segmentation images</b>.</li>
          <li>Built a <code>train / val / test = 8000 / 833 / 291</code> split, with 291 high-quality manually annotated samples as the independent test set.</li>
          <li>Introduced CE and Focal Tversky Loss into DeepLabV3+, improving mIoU from <b>78.4% to 82.4%</b>.</li>
        </ul>
      </details>

<details>
        <summary>
          <b>Intelligent Laboratory Chemical Management System</b><br>
          <sub>Face recognition · OCR · inventory audit · <a href="https://scut.leai.me">scut.leai.me</a></sub>
        </summary>
        <br>
        <p>An edge-model-based hazardous-chemical management system for laboratory intake, checkout, return, auditing, and anomaly tracking.</p>
        <ul>
          <li>Delivered and deployed the first runnable version within two days.</li>
          <li>Integrated face recognition, chemical-label OCR, and electronic-scale serial communication.</li>
          <li>Used InsightFace to associate operators with chemical transactions and abnormal events.</li>
          <li>Used RapidOCR and PaddleOCR for chemical-label recognition.</li>
          <li>Combined name normalization and fuzzy matching with an index of <b>41,977 IECSC chemical names</b>.</li>
          <li>Deployed online at <a href="https://scut.leai.me">scut.leai.me</a>.</li>
        </ul>
      </details>

<details>
        <summary>
          <b><a href="https://github.com/Argus-Agent/argus">Argus Dual-Agent System</a></b><br>
          <sub>GUI Agent · Code Agent · computer-use automation</sub>
        </summary>
        <br>
        <p>A collaborative execution framework combining a GUI Agent and a Code Agent for computer-use tasks.</p>
        <ul>
          <li>Designed Smart Router, failure fallback, Tool Calling, and Agent Memory mechanisms.</li>
          <li>Supported screenshot understanding, window control, mouse and keyboard interaction, and code execution.</li>
          <li>Used Doubao UI-TARS 1.5 7B for graphical interface understanding.</li>
          <li>Deployed OpenCUA and conducted basic evaluations on OSWorld.</li>
          <li>Developed GUI and CLI interfaces, Docker support, automated tests, and CI workflows.</li>
          <li>Open-sourced the project and released an executable version.</li>
        </ul>
      </details>

## GitHub


<p align="center">
  <img height="165" src="https://github-stats-extended.vercel.app/api?username=sudo-yf&show_icons=true&theme=transparent&hide_border=true&rank_icon=github" alt="GitHub stats" />
  <img height="165" src="https://github-stats-extended.vercel.app/api/top-langs/?username=sudo-yf&layout=compact&theme=transparent&hide_border=true&langs_count=8" alt="Top languages" />
</p>
