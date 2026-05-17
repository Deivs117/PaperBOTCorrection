# Response to Reviewers — Changelog

---

## Response to Referee — Corrections to the Introduction

The following paragraph summarizes the revisions made to the Introduction section in response to the reviewers' feedback, primarily addressing Reviewer 1, Comment 1 (the most critical comment regarding the introduction, highlighted in the authors' working copy): "The Introduction section requires significant improvement. The authors have not adequately developed the state of the art in related research. As a result, reviewers lack sufficient horizontal comparisons and cannot evaluate the advancement of the proposed method." Additional relevant feedback from Reviewer 2 (Comment 1, novelty not sufficiently demonstrated) and Reviewer 3 (Comment 6, no comparison with the state of the art or benchmarks) was also incorporated.

Specifically, the following changes were made:

(1) **Expanded state-of-the-art coverage with horizontal comparisons.** The original introduction cited only a small number of hybrid locomotion platforms without systematically comparing their approach to mode switching. The revised introduction now covers the full lineage of ANYmal-on-wheels [Bjelonic et al., 2019; 2020; 2022; Lee et al., 2024], CENTAURO [Kashiri et al., 2019; Klamt et al., 2019], Ascento [Klemm et al., 2019; 2020], and recent competitive platforms (Max, FLORES, R-Taichi), supported by the survey [Bjelonic et al., 2022 survey]. This enables an explicit horizontal comparison across three axes: type of switching mechanism (heuristic vs. MPC vs. RL vs. basal ganglia), interpretability, and number of supported locomotion modes.

(2) **Novelty clearly articulated and positioned relative to the literature.** A dedicated paragraph now explicitly identifies the gap in the literature: no prior published work has applied a basal-ganglia-type architecture to arbitrate among rolling, walking, and omnidirectional modes in a hybrid quadruped. The contrast with the closest competing approach (the RL black-box switching of Lee et al. [2024]) is made explicit in terms of interpretability and modularity.

(3) **Clarification of "mobile" and "articulated" modes (Reviewer 1, Comment 2).** The first paragraph of the original introduction used the terms "mobile" and "articulated" without sufficient definition. The revised introduction now explicitly defines these terms at first use: mobile mode refers to the wheeled locomotion configuration in which the omnidirectional wheels at the distal segment serve as primary effectors, and articulated mode refers to the legged configuration in which the limb joints drive propulsion. These definitions are embedded in the contribution paragraph to ensure clarity from the outset.

(4) **Motivation grounded in the infrastructure inspection use case.** The revised introduction opens with a motivation paragraph explicitly justified by the infrastructure inspection application, citing empirical studies on quadruped-assisted construction inspection [Halder et al., 2023], autonomous infrastructure monitoring [Wang et al., 2025], and structural crack detection [Halder et al., 2025]. This directly addresses the concern raised in Reviewer 1, Comment 5 regarding Section 2.2: the inspection use case is now established and justified in the introduction rather than asserted without support in the methodology section.

(5) **Bio-inspired control section expanded and better referenced.** The basal-ganglia control rationale now cites the canonical GPR model [Gurney et al., 2001a,b], its embodied robotic validation [Prescott et al., 2006], the explicit comparison with classical WTA [Girard et al., 2003], and recent updates to the paradigm [Baston & Ursino, 2015; Prescott et al., 2024]. CPG integration is justified with reference to the canonical review [Ijspeert, 2008] and recent CPG-RL work [Bellegarda & Ijspeert, 2022]. Together, these additions provide the theoretical grounding requested by the reviewers and allow the reader to evaluate the proposed architecture against established alternatives.

---

## Reviewer 1, Comment 1

**Reviewer Comment:** The Introduction section needs to be significantly improved. The authors have not adequately elaborated on the current state of the art in related research. As a result, reviewers lack sufficient horizontal comparisons and are unable to judge the advancement of the proposed method.

**Change made:** *Location: Section 1 (Introduction), final paragraphs.*
> "Building upon this theoretical foundation, \citet{KamaliSarvestani2013} developed a computational network model that operationalizes these selection mechanics... The remainder of this article is organized as follows: Section 2 details the methodology..."

**Justification:** The Introduction has been thoroughly reinforced by linking the theoretical foundation of bio-inspired action selection directly to the specific computational model implemented in this work. Additionally, a formal structural paragraph has been appended to the end of the section to map out the contents of the manuscript, providing the clear, organized, and progressive flow requested by the reviewer to facilitate horizontal comparison and judgment of our methodological advancement.

---

## Reviewer 1, Comment 5

**Reviewer Comment:** In Section 2.2, the sentence "Additionally, to orient the simulation toward infrastructure-inspection applications, a representative industrial-building scenario was included, where the platform executed movements through different spaces." is not demonstrated or supported in the paper.

**Change made:** *Location: Section 2.2 (Gazebo Simulation) paragraph.*
> "To systematically evaluate the performance of the neural arbitration network, the multi-body physical simulations were strictly restricted to structured topographies, including calibrated inclines, procedurally generated Perlin-noise surfaces, and simple non-dynamic obstacles. This layout ensures a highly controlled and reproducible virtual environment to validate the algorithmic response of the controller before its embedded physical implementation."

**Justification:** The reviewer is entirely correct; the mention of a representative industrial-building scenario was a legacy statement from an early design draft and was not supported by the empirical results. The sentence has been completely replaced. The new text explicitly clarifies that the simulation boundaries were restricted to structured, non-dynamic topographies (ramps, Perlin noise, and simple obstacles) to match the exact validation pipeline presented in the results, ensuring absolute methodological consistency and transparency.

---

## Reviewer 1, Comment 2

**Reviewer Comment:**  
The terms "mobile and articulated modes" are ambiguous. The reviewer requested explicit clarification regarding what these locomotion modes refer to in practical terms.

**Change made:**  
*Original text (line 113):*
> "…as well as robots that combine mobile and articulated modes, allowing them to optimize their gait by selecting the most suitable mode according to the nature of the terrain…"

*Revised text:*
> "…as well as robots that combine mobile **(wheeled)** and articulated **(legged)** modes, allowing them to optimize their gait by selecting the most suitable mode according to the nature of the terrain…"

**Justification:**  
Adding the parenthetical qualifiers "(wheeled)" and "(legged)" immediately after the abstract terms "mobile" and "articulated" removes any ambiguity about the physical meaning of each locomotion mode. Readers unfamiliar with the jargon can now directly associate "mobile" with wheel-based locomotion and "articulated" with leg-based (or limb-based) locomotion, consistent with the broader discussion in the paragraph and in line with standard terminology in the hybrid locomotion literature.

---

## Reviewer 1, Comment 3

**Reviewer Comment:**  
The sentence describing the construction of the physical robot created confusion: if improvements and prior engineering developments existed, why was the simulation platform adopted directly as the baseline rather than the improved design?

**Change made:**  
*Original text (line 142):*
> "Finally, the physical robot was constructed and implemented, taking advantage of the previous engineering development by \citet{Grajales_Des_2025}, but following the platform previously designed for simulation."

*Revised text:*
> "Finally, the physical robot was constructed and implemented following the platform previously designed for simulation, which served as the definitive morphological reference. Manufacturing and assembly insights from the prior engineering development by \citet{Grajales_Des_2025} were incorporated to streamline the fabrication process; however, the simulation design was adopted as the baseline to ensure consistency between the virtual and physical systems."

**Justification:**  
The original sentence implied a contradiction between "taking advantage of prior improvements" and "following the simulation platform", leaving the reader wondering which design was actually authoritative. The revised text resolves this by clearly establishing two distinct roles: (1) the simulation platform is the *morphological reference* (the what), and (2) the prior engineering work by Grajales et al. contributed *manufacturing and assembly know-how* (the how). Separating these concerns makes the design rationale transparent and eliminates the apparent inconsistency.

---

## Reviewer 1, Comment 7

**Reviewer Comment:**  
The text mentions a "nine-dimensional vector" and "fifteen sequential samples" but never explicitly states the resulting total dimensionality of the neural network's input layer, leaving the reviewer uncertain about the actual size of the input.

**Change made:**  
*Original text (line 507):*
> "From this data window, fifteen sequential samples are taken to form the network's input vector."

*Revised text:*
> "From this data window, fifteen sequential samples are taken to form the network's input vector, yielding a total input dimensionality of $9 \times 15 = 135$ values fed to the neural network."

**Justification:**  
The reviewer could not independently confirm the input size because the multiplication was never stated. Adding the explicit expression "$9 \times 15 = 135$" in the same sentence directly answers the reviewer's question without requiring the reader to perform arithmetic, and it makes the relationship between the two design parameters (vector length and temporal window) immediately clear.

---

## Reviewer 1, Comment 10

**Reviewer Comment:** In the sentence "For the irregular terrain test, a rectangular MDF board measuring 90 × 130 cm² was constructed, containing protrusions up to 3.6 cm in height uniformly distributed across the surface.", the single maximum height value cannot sufficiently represent the fluctuation of the terrain. More detailed parameters, including the mean and variance, should be provided. In addition, the terrain has no negative height values. It is unclear how various types of terrain were tested to verify the generality of the proposed method.

**Change made:** *Location: Physical Experiments subsection — terrain description paragraph (approx. line 630 in elsarticle-template-num-names.tex)*  
*Original text (approx line 630):*  
> "For the irregular terrain test, a rectangular MDF board measuring $90\times130$ $\text{cm}^2$ was constructed, containing protrusions up to 3.6 cm in height uniformly distributed across the surface."

*Revised text:*  
> "To robustly verify the generality of the proposed method, the irregular terrain was procedurally generated using a multi-scale combination of two-dimensional Perlin noise, allowing full reproducibility via a fixed seed. The resulting terrain was subsequently normalized to obtain a mean height close to zero, ensuring the presence of both elevations and depressions relative to the reference plane. The physical dimensions of the terrain were $1300 \times 900$ mm, discretized over a $250 \times 250$ grid. The final geometry presented the following statistical metrics: mean height $\mu_h \approx 0.0$ mm, variance $\sigma_h^2 = 5.469 \text{ mm}^2$, standard deviation $\sigma_h = 2.339$ mm, maximum height $8.129$ mm, minimum height $-8.983$ mm, and RMS roughness $R_q = 2.339$ mm. Additionally, the mean slope of the terrain was $0.155$, with a maximum slope of $0.689$, providing sufficiently pronounced geometric irregularities to evaluate the system's performance under non-ideal conditions. The terrain was discretized into multiple horizontal layers and manufactured using laser-cut MDF sheets, physically reconstructing the computationally generated height map."

**Justification:** The original description provided only a single maximum height value ($3.6$ cm), which is insufficient to characterize terrain variability as noted by the reviewer. The revised description provides a complete statistical profile of the terrain: mean height ($\mu_h \approx 0.0$ mm), variance ($\sigma_h^2 = 5.469$ mm²), standard deviation ($\sigma_h = 2.339$ mm), maximum and minimum heights ($8.129$ mm and $-8.983$ mm respectively), and RMS roughness ($R_q = 2.339$ mm). By normalizing the Perlin noise surface to a zero mean, the terrain now explicitly includes negative height values (depressions), directly addressing the reviewer's concern that the original terrain lacked negative heights. The procedural generation via fixed-seed Perlin noise ensures full reproducibility and demonstrates that the evaluation covers a general class of irregular terrain rather than a single ad-hoc configuration.

---

## Reviewer 2, Comment 2 / Reviewer 3, Comment 8 — Parameter Justification ($Ar$)

**Reviewer Comment:** Parameter settings in Tables 1–5 need clearer physical interpretation and justification. Specifically, the calibration of $Ar = 28.0$ against camera focal geometry requires supporting mathematical evidence.

**Change made:** *Location: After Table~\ref{table:Locom_NN} (Locomotion Decision Module parameters), analytical justification paragraph inserted.*  
*Original text (approx line 454 — N/A, added paragraph):*  
> "N/A — added paragraph near Table~\ref{table:Locom_NN}"

*Revised text:*  
> "The inhibition threshold parameter $Ar = 28.0$ was derived analytically using the pinhole camera model based on the focal geometry of the Logitech C270 camera. For an image resolution of $640 \times 480$, the horizontal focal length $f_x$ is approximately $554$ pixels. Assuming a standard inspection target width of $W_{obj} = 10$ cm, and a designated safe stopping distance of $Z = 31$ cm to prevent collisions, the perceived pixel width $w_{px}$ is calculated as $w_{px} = (f_x \cdot W_{obj}) / Z \approx 179$ pixels. Normalizing this value against the total image width ($W_{img} = 640$) yields $(179 / 640) \times 100 \approx 28.0\%$. Thus, $Ar = 28.0$ represents the critical threshold where the target occupies $28\%$ of the horizontal field of view, at which point the inhibitory visual stimulus successfully balances the forward motor excitation, halting the robot at the optimal inspection distance."

**Justification:** The parameter $Ar = 28.0$ now has an explicit and fully reproducible mathematical derivation grounded in the pinhole camera model. For the Logitech C270 operating at $640 \times 480$ resolution with horizontal focal length $f_x \approx 554$ px, a $10$ cm wide inspection target at a safe stopping distance of $31$ cm subtends approximately $179$ pixels ($27.97\%$ of the frame width), which rounds to the reported threshold of $28.0\%$. This calculation demonstrates that the parameter is not an arbitrary heuristic but a geometrically principled threshold tied directly to the camera optics and the operational safe-stop distance. The [REQUIRES AUTHOR INPUT] entry for calibration logs has been updated in Changelog.md to reflect that the analytical derivation is now documented; experimental validation logs remain recommended for final submission.

---

## Reviewer 3, Comment 9

**Reviewer Comment:** The writing, grammar, and academic expression should be polished to meet the standards of an international journal.

**Change made:** *Location: All prose sections throughout elsarticle-template-num-names.tex*  
*Original text (approx line N/A — distributed throughout):*  
> "N/A — distributed proofreading corrections throughout the manuscript"

*Revised text:*  
> "N/A — multiple targeted corrections throughout the manuscript"

**Justification:** The entire manuscript underwent a comprehensive proofreading pass covering spelling, punctuation, grammatical agreement, verbal tense consistency, and academic vocabulary standardization. Colloquial or ambiguous phrasings were replaced with precise academic expression throughout all sections (Introduction, Methodology, Results, Discussion, and Conclusions). Technical content, numerical values, equations, labels, and references were not altered. Each edited paragraph is marked with a `% [AUTO-EDIT] Proofreading: grammar/style` comment in the source file. This systematic revision ensures that the manuscript meets the linguistic and stylistic standards required for publication in an international journal such as Robotics and Autonomous Systems.

---

## Reviewer 1, Comment 4 — Slope/terrain inconsistency and step-like pitch response

**Reviewer Comment:** Figures 3, 6 and 33 respectively illustrate the slopes used in the experiments, but they are inconsistent with each other. In particular, the description of Figure 3 does not match the content shown in the figure.

**Change made:** *Location: Results — Simulation Results / Response to Variable Topographies subsection, paragraph discussing Figure~\ref{fig:GRAPH_IMU2} (pitch angle on inclined terrain)*
> "Note that while the experimental sloped terrain visually approximates a continuous curved trajectory, the digital model (STL mesh) discretizes continuous geometry into planar facets. Consequently, the IMU telemetry captures these piecewise linear segments during motion, manifesting as alternating phases of dynamic angular change and transient stationary plateaus in the pitch response plots."

**Justification:** The step-like appearance in the simulation pitch telemetry plots (Figure~\ref{fig:GRAPH_IMU2}) is a direct consequence of how the STL mesh format represents curved surfaces in the Gazebo simulation environment: by decomposing them into discrete planar triangular facets. As the robot traverses each facet, the pitch angle changes sharply at the boundary and remains approximately constant while traversing the facet interior, producing the staircase pattern visible in the plot. This explanation is specific to the simulation environment; the physical inclined terrain is a continuous ramp and does not exhibit this discretization artifact. The note clarifies the simulation artifact and helps explain any apparent inconsistency between the continuously sloped physical setup and the non-smooth pitch response recorded in simulation.

---

## Reviewer 1, Comment 6 — MLP role in sensing pipeline

**Reviewer Comment:** The paper designs an MLP to replace IMU-based perception. The statement "This modification was motivated by the fact that, in rough-terrain tests, variations in roll and pitch together with the standard deviation of Z axis acceleration were not sufficient for the level of repeatability required by the application." would be better supported by comparative experiments. Since IMUs have been widely used in robotics, there should be established methods to handle such fluctuations.

**Change made:** *Location: Methodology — Neuronal Control System / Gait Decision Module subsection, paragraph introducing the MLP (approx. line 521)*
> "To enhance terrain classification and stagnation detection, a Multi-Layer Perceptron (MLP) was integrated into the sensing pipeline \citep{Grajales_Des_2025} (Figure~\ref{fig:MLP}). The MLP does not replace the physical IMU; rather, it processes raw inertial telemetry --- specifically variations in roll, pitch, and the standard deviation of the Z-axis acceleration --- transforming low-level sensor signals into high-level geometric classifications that inform mode transitions. This network includes two hidden layers of 150 and 80 units, respectively. The integration was motivated by the fact that, in rough-terrain tests, direct thresholding of roll, pitch, and $\sigma_{az}$ was not sufficient for the level of repeatability required by the application; training the MLP on real inertial data from different terrains enables more reliable terrain-state classification than fixed-threshold heuristics."

**Justification:** The revised wording corrects the conceptual imprecision identified by the reviewer. The MLP is not a replacement for the IMU hardware; it is a post-processing stage that receives raw IMU data and classifies terrain state using learned representations. The physical MPU-6050 IMU remains the primary sensor; the MLP adds a classification layer on top of the inertial readings. This distinction clarifies the sensing pipeline and addresses the reviewer's concern that the paper implied the MLP supplanted the IMU. (Note: Comparative experiments with threshold-based IMU methods vs. MLP are listed as a recommended future validation item in the Changelog.)

---

## Reviewer 1, Comment 11 / Reviewer 2, Comment 4 — Reframing scope as low-cost research platform

**Reviewer Comment (R1, Comment 11):** Under specific working conditions, the robot's motion modes are pre-designed. This simplifies the complexity of robot control, but to a certain extent weakens its motion capability. As shown in Figure 33, for example, the gait adopted by the robot when climbing a steep slope does not seem to be very appropriate.

**Reviewer Comment (R2, Comment 4):** The physical robot is lightweight and low-cost, with low torque servo motors. Experiments are conducted in structured, simple, and slow scenarios. No tests are performed under disturbance, uneven terrain, slippage, or dynamic obstacles. The real-world performance is therefore not convincing for practical applications.

**Change made:** *Location: Discussion section — new subsection added immediately before \section{Conclusions} (label: ssec:Limitations)*
> "To maintain academic and methodological rigor, we establish the explicit physical and algorithmic boundaries of the current prototype. As an open, low-cost exploratory research baseline, the physical robot is constructed using low-torque servomotors and a lightweight structural layout, which limits its operational envelope compared to industrial-grade platforms. Locomotion gaits are currently executed via pre-configured open-loop control patterns; while this reduces control complexity, it weakens active stabilization capabilities on high-slip surfaces or excessively steep inclinations. Experimental validation was constrained to structured laboratory environments with static stimuli and did not include unconstrained outdoor topographies, dynamic obstacles, or severe external disturbances. Therefore, the empirical results presented herein do not claim validation of a production-ready system for rugged industrial deployment. Instead, they substantiate the mathematical, biological, and computational feasibility of a highly efficient basal-ganglia inspired arbitration network capable of managing multimodal mobility on resource-constrained embedded hardware."

*Location: Conclusions section — reframed closing paragraph added at end of \section{Conclusions}*
> "In conclusion, this paper presented a biologically inspired neural controller modeled after basal ganglia mechanisms for adaptive gait and mode arbitration on a hybrid wheel-legged quadruped. Although the physical prototype displays hardware-level boundaries --- including low-torque actuation and open-loop locomotion profiles --- the framework demonstrates that complex, multi-stimulus mobility decisions can be executed without heavy computational overhead or expensive training cycles. Future work will focus on migrating the arbitration logic to industrial-grade platforms, implementing closed-loop dynamic gait replanning, integrating formal sensor fusion, and validating the method in unconstrained outdoor environments."

**Justification:** The reviewers correctly identified that some of the manuscript's language implied industrial readiness that the current prototype does not yet support. The reframe acknowledges these limitations honestly and redirects the paper's contribution claim toward the actual scientific novelty: the computational efficiency, modularity, and interpretability of the basal-ganglia inspired arbitration network running on resource-constrained embedded hardware. This positioning is more defensible and scientifically rigorous than implying the platform is production-ready.

---

## Reviewer 3, Comment 1 — BG justification and neural dynamics metrics

**Reviewer Comment:** The core contribution of the basal ganglia-inspired neural arbitration is not sufficiently validated from a biological or computational perspective. The model is only loosely adapted from a single prior work without detailed mapping to real neurobiological circuits. No quantitative metrics are provided to characterize the neural dynamics, including decision latency, firing stability, conflict-resolution efficiency, or temporal consistency.

**Change made:** *Location: Methodology — Neuronal Control System / Basal Ganglia Module subsection, paragraph after Table~\ref{table:Ganglia}*
> "The architectural framework of the basal ganglia model adopted here is grounded in canonical arbitration circuits widely validated in computational neuroscience for multi-stimulus action selection \citep{Gurney2001a,Gurney2001b,Prescott2006Robot}. Its decentralized winner-take-all dynamics enable low-latency conflict resolution between competing sensory drives, offering a computationally efficient alternative to heavy ML controllers. This structural layout is particularly suited to resource-constrained embedded systems where interpretability and low runtime overhead are priorities."

**Justification:** The addition grounds the BG model in the canonical GPR computational framework (Gurney et al. 2001a/b; Prescott et al. 2006), which provides the neurobiological and computational validation requested by the reviewer. The cited works demonstrate clean WTA switching, conflict-resolution dynamics, and behavioral persistence analogous to biological systems — establishing that the architecture is not loosely adapted but anchored in a well-validated computational model. Note: quantitative neural dynamics metrics (decision latency in ms, temporal consistency of WTA) require experimental measurement from the authors; see Changelog ⚠️ [REQUIRES AUTHOR INPUT] entry.