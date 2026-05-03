# Response to Reviewers — Changelog

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
