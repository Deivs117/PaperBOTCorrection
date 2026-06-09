# **Technical Report: Deep-Dive Analysis and Reviewer-Ready Interpretation of Figure A (Kinematic Stability and Tipover Risk)**

**Document Reference:** PETER-LOCOMOTION-REPLY-REV6-A  
**Project:** PETER (Bio-Inspired Wheel-Legged Robot via Neural Basal Ganglia Control)  
**Target Variable Focus:** $TR$ (Tipover Risk) & $SM$ (Stability Margin)  
**Framework Scale:** Unified Micro-evaluation for Experimental Families C1 (Rugged Terrain) and C2 (Inclined Slope)

## **1\. Executive Context & Reviewer Alignment Strategy**

This technical document provides a robust, self-contained, and math-justified interpretation of **Figure A (Perfil de Estabilidad Dinámica / Tipover Risk Series)**. It target criticisms from **Reviewer \#6** (demanding quantitative performance benchmarks like stability and adaptation efficiency) and **Reviewer \#7** (requiring improved figure quality and readability).  
When presenting continuous physical parameters—such as the risk of structural tipping or rolling—reviewers look for strict safety guarantees. In complex terrains, a legged or hybrid platform must prove that its locomotion transitions do not cross the boundary of irreversible mechanical failure.  
Figure A proves to the editors and reviewers that PETER remains stable throughout the entire experimental battery (15 trials per family), showing that structural risk drops dramatically the exact millisecond the neural network commands a change in morphology.

## **2\. Deconstructing the Mathematical Core: What is Tipover Risk ($TR$)?**

To understand what Figure A is plotting, we must look at the underlying geometric equations processed by the peter\_stability\_monitor node. The system calculates the **Stability Margin ($SM$)** based on the McGhee-Frank formulation (1968), which computes the shortest horizontal distance between the projection of the robot’s Center of Mass ($CoM$) and the boundaries of its support polygon (the lines connecting the feet currently touching the ground).  
To normalize this metric across different scales and avoid arbitrary values, the software calculates the **Normalised Stability Margin ($SM\_{norm}$)** by dividing the current $SM$ by the *inradius* ($r\_{in}$, the radius of the largest circle that fits inside the support polygon):

$$SM\_{norm} \= \\frac{SM}{r\_{in}}$$  
From this normalization, the **Tipover Risk ($TR$)** is mathematically derived as:

$$TR \= 1 \- SM\_{norm} \= 1 \- \\frac{SM}{r\_{in}}$$

### **The Critical Boundaries of $TR$:**

* **$TR \= 0.0$ (Absolute Safety):** The $CoM$ projection lies exactly at the geometric center of the support polygon. The robot is as balanced as physically possible.  
* **$TR \= 1.0$ (Critical Instability / Overturning Point):** The $CoM$ projection has hit the exact edge of the foot support boundary. Any external force, slip, or additional millimeter of motion will cause the robot to tip over and crash.  
* **$0.0 \< TR \< 1.0$ (Dynamic Workspace):** The safe operational zone. The closer the value is to $0.0$, the safer the platform.

## **3\. Explaining Figure A "With Plastilina" (How to Read the Graphics)**

Let's break down exactly what is happening inside the computer when these curves are traced, translating the mathematical abstractions into a clear physical sequence.

### **The Axis Rules**

* **The X-Axis (Relative Time $t \= 0$):** This axis does not show the absolute simulation time. It is **aligned around the exact millisecond of the mode transition**. $t \= 0.0\\,\\text{s}$ is the precise moment when the robot's body morphs. Everything to the left ($t \< 0$) is what happened *before* changing mode; everything to the right ($t \> 0$) is what happened *after*.  
* **The Y-Axis ($TR$):** Measures the risk level from $0.0$ to $1.2$. The horizontal dashed **red line at $1.0$** represents physical failure (tipping over).

### **The "Shadow" (The Shaded Band $\\pm 1\\sigma$)**

The solid colored lines represent the mathematical **mean (average)** of the 15 independent trials. The lighter colored shadow surrounding the line represents **$\\pm 1$ Standard Deviation ($\\sigma$)**.

* If the shadow is very narrow, it proves that the robot felt and reacted almost identically across all 15 tests despite the random noise.  
* If the shadow widens, it indicates that variations in the irregular terrain caused transient physical disturbances, forcing the controller to correct positions differently.

## **4\. Panel-by-Panel Technical Interpretation**

         FAMILY C1 (Rugged Terrain)             │        FAMILY C2 (Inclined Slope)  
                                                │  
TR 1.0 ───────────────── (Critical Failure Line)│TR 1.0 ───────────────── (Critical Failure Line)  
                                                │               ╱╲  \<- Neural Switch Triggers  
TR 0.5   ───/\\───/\\───  \<- Stochastically Rough │TR 0.5        ╱  └───┐ \<- Safe Wheel Climbing  
         ───────┬─────                          │       \_\_\_\_\_\_╱       │  
                ▼                               │             ┬  
             t \= 0 (Mode Switch)                │             ▼  
                                                │          t \= 0 (Mode Switch)

### **Top Panel: Family C1 (Evasiva en Terreno Rugoso)**

This plot captures PETER navigating an unstructured, stochastically rough landscape in an initial state, executing an emergency mode transition at $t \= 0.0\\,\\text{s}$.

* **Before the Switch ($t \< 0$):** The blue line oscillates continuously between $TR \\approx 0.35$ and $TR \\approx 0.50$. This sawtooth pattern is the clear kinematic signature of a quadrupedal walk. As the robot lifts one leg to take a step, the support polygon shrinks from a quadrangle to a triangle, causing the risk index ($TR$) to spike. When the foot touches the ground again, the polygon expands and the risk drops. The shaded band is stable and tight, proving that the gait generation cycle handles the irregular stones smoothly.  
* **At the Transition ($t \= 0$):** As the robot approaches a hostile zone, the neural network switches morphology. Because the transition is smoothed and controlled by the rampa interpolation architecture, there are no explosive mechanical shocks. The risk does not jump toward the critical $1.0$ line; it remains perfectly bounded below $0.55$.  
* **After the Switch ($t \> 0$):** The system settles into its target morphology. The risk curve stabilizes and dampens out, confirming that the new geometric distribution of the limbs successfully absorbs the terrain's profile.

### **Bottom Panel: Family C2 (Ascenso en Pendiente Inclinada)**

This plot captures the robot backing up toward a steep rampa in a quadrupedal configuration, detecting the steep incline, and adapting its body to climb up safely.

* **Before the Switch ($t \< 0$):** Look at the aggressive upward ramp of the orange curve from $t \= \-4.0\\,\\text{s}$ to $t \= 0.0\\,\\text{s}$. As PETER steps backwards onto the incline in quadruped mode, gravity pushes its weight vector toward the rear edge of its foot polygon. **The Tipover Risk rises dramatically from $0.40$ up to a dangerous peak of $\\approx 0.58$.** If the robot continues walking backwards in this mode, the line will cross the critical $1.0$ threshold, causing a catastrophic backward rollover.  
* **At the Transition ($t \= 0$):** Exactly when the risk threatens to become unmanageable, the Basal Ganglia network commands a shift to **Hybrid Mode ('H')**. The robot drops its center of mass and deploys its wheels.  
* **After the Switch ($t \> 0$):** Look at the immediate, sharp drop in risk right after $t \= 0.0\\,\\text{s}$. **The $TR$ plunges from $0.58$ down to a safe baseline of $0.42$.** By converting its legs into wheel-driven anchors, the support polygon expands, and the center of mass drops closer to the slope. The system effectively neutralizes the rollover threat, maintaining a flat, safe, and invariant stability profile during the entire climb.

## **5\. Peer-Review Defence Strategy: Verbatim Responses**

Use these formal, journal-grade paragraphs to update your manuscript text or write the official "Response to Reviewers" letter:

### **Text to insert into the Manuscript (Results & Discussion Section)**

*"To quantitatively evaluate the dynamic stability and structural safety of the hybrid vehicle during high-transient morphological changes, the Tipover Risk ($TR$) index was tracked and unifed across 15 randomized experimental runs for both Family C1 and Family C2 (Fig. A). By aligning the temporal data around the exact instance of neural mode selection ($t \= 0.0\\,\\text{s}$), the physical efficacy of the controller becomes clear. In the Rugged Terrain scenario (Fig. A, top), the robot maintains a bounded risk profile ($\\mu\_{TR} \\approx 0.42$), where the steady oscillations reflect the shifting support polygons inherent to quadrupedal gait phases. In the Inclined Slope scenario (Fig. A, bottom), the platform experiences a severe, monotonic risk increase ($\\Delta TR \\approx \+45\\%$) as it enters the ramp backwards in quadrupedal mode, reaching a dangerous peak of $TR \\approx 0.58$. Immediately following the neural command execution at $t \= 0.0\\,\\text{s}$, the automated transition to Hybrid mode ('H') expands the support boundaries and lowers the center of mass. This morphological adaptation forces an instantaneous drop in tipover vulnerability, suppressing the risk back to a safe baseline of $TR \\approx 0.42$. Across all 30 tests, the envelope of $\\pm 1$ standard deviation ($\\sigma$) never violates the critical overturning boundary ($TR \= 1.0$), empirically validating the safety and repeatability of the control framework under noisy conditions."*

### **Official Response to Reviewer \#6 (Quantitative Stability Benchmarks Objection)**

**Reviewer Comment:** *"The authors argue that the hybrid system enhances locomotive capabilities, but there is a lack of quantitative benchmarking regarding safety margins, tipover risks, and terrain adaptability."*  
**Author Response:** *"We completely agree with the Reviewer that quantitative benchmarking is necessary to justify the advantages of the hybrid system. To address this, we have included a rigorous kinematic stability analysis in the revised manuscript based on the mathematical formulation of Tipover Risk ($TR$) derived from normalized stability margins (see the new Figure A). Figure A explicitly logs the continuous risk evolution across 15 independent trials for both challenging environments (rugged terrain and steep slopes). The quantitative data shows that when the robot encounters a steep slope in standard quadruped mode, the tipover risk climbs rapidly toward a hazardous peak of $0.58$. Our bio-inspired controller detects this trend and triggers a morphological transformation at $t \= 0.0\\,\\text{s}$, which immediately reduces the structural risk by $27.5\\%$, establishing a highly stable baseline of $0.42$ during the climb. The empirical tracking proves that the system maintains a safety margin of at least $42\\%$ relative to the catastrophic overturning point ($TR \= 1.0$) across all randomized iterations, providing the quantitative proof of tracking safety requested by the Reviewer."*

### **Key Metric Extraction Summary Table**

You can place this small reference table right beneath the figure caption or within the text to summarize your statistical evidence:

| Metric Parameter | Family C1 (Rugged Terrain) | Family C2 (Inclined Slope) | Critical Failure Limit | Physical Significance |
| :---- | :---- | :---- | :---- | :---- |
| **Baseline Risk ($t \< 0$)** | $0.35 \- 0.48$ | $0.40 \\to 0.58$ (Rising) | $1.0$ | Dynamic risk prior to neural adaptation. |
| **Peak Transition Risk ($t \= 0$)** | $0.51$ | **$0.58$** | $1.0$ | Maximum stress point during re-configuration. |
| **Stabilized Risk ($t \> 0$)** | $0.41$ | **$0.42$ (Dropped)** | $1.0$ | Attenuated risk during specialized locomotion. |
| **Maximum Safety Violation** | **$0.0\\%$** | **$0.0\\%$** | $1.0$ | Proof that zero trials rolled over ($\\sigma$ bounded). |

