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