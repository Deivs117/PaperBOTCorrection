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

---

## Changelog — AUTO-EDITS

All changes listed below were applied automatically to `elsarticle-template-num-names.tex`. Equation expressions and numerical values were not modified; only explanatory prose was added or reorganized.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added definitions for `τ_Z` and `σ_Z` immediately after Equation `\eqref{eq:ring}` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** These parameters appeared in eq. (ring) but were not defined in the immediately preceding text.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added sentence defining `τ_L`, `τ_IRA`, `ω_{Z→L}`, `ω_{L→L}`, and the `W` inter-layer matrices after `Table~\ref{table:LiDAR}` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 1):** These constants appear in the table with numeric values but lack physical descriptions in the surrounding prose.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Extended the explanatory paragraph following Equations `\eqref{eq:L0}`–`\eqref{eq:L4}` to explicitly define `τ_L` and `τ_IRA` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** The existing paragraph defined layer variables but omitted the time-constant symbols.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added "where…" sentence after Equations `\eqref{eq:stn}`–`\eqref{eq:str}` defining `STN[i]`, `Gpi[i]`, `Gpe[i]`, `STR[i]`, `R_i`, and all four time constants (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** None of these variables were defined in the immediately preceding text.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added sentence after `Table~\ref{table:Ganglia}` defining the time constants, `ω_{X→Y}` notation, and flagging `μ_{STN}` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 1):** Physical meaning of Basal Ganglia table parameters was absent from surrounding prose.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added "where…" sentence after Equations `\eqref{eq:Z_5}`–`\eqref{eq:Z_6}` defining `τ`, `ω_{L→X}`, `L_2`, `L_4` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** These appeared in equations without local definition.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added "In Equations…" sentence after Equations `\eqref{eq:Z_3}`–`\eqref{eq:Z_17}` defining `Gpe_B`, `Gpe_G`, `Gpe_R`, `w`, and `Ar` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** These symbols were used throughout the locomotion decision module equations without a local definition.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added "where…" sentence after Equation `\eqref{eq:Naka}` defining `x`, `A`, and `σ` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** The preceding text mentioned `(·)_+` but did not define `A` or `σ`.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added `% [REF]` comments after Equations `\eqref{eq:NakaImu}` and `\eqref{eq:NakaMode}` pointing back to definitions in `\eqref{eq:Naka}` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** Same structure/symbols as eq. (Naka); cross-referenced per instructions.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added "In Equations…" sentence after Equations `\eqref{eq:Z0}`–`\eqref{eq:Z16}` defining `σ_{az}`, `U_{σ_{az}}`, `Roll`, `Pitch`, `U_{Roll}`, `U_{Pitch}`, `G_{pe,y}`, `G_{pi,x}`, `G_{pi,z}`, and `w` (with `% [REF]`) (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** IMU and GPe/GPi signals entered the gait-mode equations without local definitions.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added sentence after `Table~\ref{table:Locom_NN}` providing physical definitions for `τ`, `ω_{L→X}`, `θ_p`, `HI`, thresholds, `A`, `Ar`, `σ_M`, `σ_I` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 1):** Table lists numeric values without physical descriptions in surrounding text.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added "In Equations…" sentence after Equations `\eqref{eq:Z0V2}`–`\eqref{eq:Z16V2}` defining `N_0`, `N_1`, `N_2`, `U_{N_0}`, `U_{N_1}` and adding `% [REF]` for `w` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 2):** MLP output symbols were not defined in the immediately preceding text.

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Added sentence after `Table~\ref{table:Locom_MLP}` defining `U_{N_0}` and `U_{N_1}` (`% [AUTO-EDIT]`).  
  **Justification (TAREA 1):** Table provides threshold values with no physical description.

- **File:** `elsarticle-template-num-names.tex`  
  **Change (TAREA 3):** Reorganized `\section{Results}` by creating `\subsection{Simulation Results}` and `\subsection{Physical Implementation Results}`, each with three `\subsubsection` entries: *Single Stimulus Response*, *Response to Multiple Stimuli of Different Natures*, and *Response to Variable Topographies*. All `\label{}` and `\ref{}` commands are unchanged. Specific moves:
  - **Sim → Simulation Results / Single Stimulus:** Figs `fig:RESPUESTAS_EST_UNI`, `fig:NEU_EST_UNIG`, `fig:NEU_EST_UNIB`.
  - **Real → Physical Results / Single Stimulus:** Figs `fig:RESPUESTAS_EST_UNI_real`, `fig:NEU_EST_UNIG_real`.
  - **Sim → Simulation Results / Multiple Stimuli:** Figs `fig:NEU_EST_MUL`, `fig:RES_EST_MUL`.
  - **Real → Physical Results / Multiple Stimuli:** Figs `fig:NEU_EST_MUL_real`, `fig:robot-6frames`.
  - **Sim → Simulation Results / Variable Topographies:** Figs `fig:RES_IMU`, `fig:NEU_IMU`, `fig:GRAPH_IMU`, `fig:NEU_IMU2`, `fig:RES_IMU2`, `fig:GRAPH_IMU2`.
  - **Real → Physical Results / Variable Topographies:** Figs `fig:RES_IMU_real`, `fig:NEU_IMU_real`, `fig:GRAPH_IMU_real`, `fig:RES_IMU2_real`, `fig:NEU_IMU2_real`, `fig:GRAPH_IMU2_real`.

---

## [REQUIRES AUTHOR INPUT] Parameter Justification

The following parameters appear in tables or equations with a numeric value but without justification or literature reference. Authors must provide explanation, citation, or experimental criterion for each before final submission.

- **`j`** (location: `Equation~\eqref{eq:Z_4}`): appears as a coefficient of `Gpe_R` in `(Gpe_G + j Gpe_R)_+` — **Clarify what `j` represents** (scalar weight, index, or typo). If a weight, add its value to `Table~\ref{table:Locom_NN}`.

- **`w`** (location: `Equations~\eqref{eq:Z_7}`–`\eqref{eq:Z_17}`, `\eqref{eq:Z0}`–`\eqref{eq:Z16}`, `\eqref{eq:Z16V2}`): not explicitly listed in tables — **State whether `w` is a single global inhibitory weight (provide value) or shorthand for different ω values per connection.** Update `Table~\ref{table:Locom_NN}` accordingly.

- **`μ_{STN}`** (location: `Table~\ref{table:Ganglia}`): value = 1.0 — **Confirm its role and which equation/term it modulates**, or remove from table if unused.

- **`ω_{Z→L}`, `ω_{L→L}`** (location: `Table~\ref{table:LiDAR}`): heuristic weights — **Provide design rationale** (sensitivity analysis, reference, or experimental justification).

- **`W_{Z→I}`, `W_{I→R}`, `W_{R→A}`, `W_{A→L4}`** (location: `Table~\ref{table:LiDAR}`): — **State whether these are fixed binary/uniform matrices or learned. Explain the design rationale.**

- **`W^{RR}`** (location: `Equation~\eqref{eq:ResL}`): recurrent weight in response layer — **Confirm whether its value equals `W_{I→R}` or is distinct, and add it explicitly to `Table~\ref{table:LiDAR}`.**

- **`ω_{L→X}`** (location: `Table~\ref{table:Locom_NN}`): value = 160.0 — **Justify the large amplification factor** (heuristic gain-tuning criterion, normalization argument, or reference). Value is ~160× larger than other weights.

- **`ω_{Gpe_R→X4}`** (location: `Table~\ref{table:Locom_NN}`): value = 2.0 — **Explain the asymmetry** with respect to `ω_{Gpe_G→X4}` = 1.0 (behavioral property encoded by this asymmetry).

- **`ω_{X4→X7}`, `ω_{X3→X8}`** (location: `Table~\ref{table:Locom_NN}`): value = 10.0 each — **Justify the non-unity value** (heuristic tuning or derived criterion).

- **`Ar`** (location: `Table~\ref{table:Locom_NN}`): value = 28.0 — **Explain origin of approach-stop threshold** (distance criterion, sensor range, or empirical tuning).

- **`HI`** (location: `Table~\ref{table:Locom_NN}`): value = 3.0 — **Justify the hunting-instinct baseline** (calibration against background noise level, or experimental selection).

- **`σ_M`** (location: `Table~\ref{table:Locom_NN}`): value = 0.3 — **Explain choice of mode-selection Naka–Rushton half-saturation constant** (dynamic range of input, empirical reference).

- **`σ_I`** (location: `Table~\ref{table:Locom_NN}`): value = 1.5 — **Explain choice of IMU Naka–Rushton half-saturation constant** (expected IMU signal range, empirical reference).

- **`U_{N_0}`** (location: `Table~\ref{table:Locom_MLP}`): value = 3.7 — **Justify the flat-terrain MLP output threshold** (statistical criterion on training data, ROC analysis, or empirical selection).

- **`U_{N_1}`** (location: `Table~\ref{table:Locom_MLP}`): value = 7.8 — **Justify why this threshold differs substantially from `U_{N_0}`** (asymmetric sensitivity, false-positive risk, or empirical tuning).

---

### Action Plan: Figure Improvements

> **Note:** No image files have been modified by this bot. All items below are manual tasks for the authors. Priority: **High** (affects reviewer acceptance), **Medium** (strongly recommended), **Low** (good practice).

#### A. Slope/Inclination Consistency — High Priority

- **Fig label:** `\label{fig:Terreno_incli}` (file: `TERRENO_INCLINADO.jpeg`)  
  **Problem:** Physical photo of the inclined terrain; slope angle may be inconsistent with descriptions and IMU readings in `fig:GRAPH_IMU2`. Reviewers 1 and 3 flagged slope inconsistencies.  
  **Action:** Verify terrain angle matches the declared 20° incline; replace image if incorrect. Regenerate at ≥ 300 DPI, add angle annotation or scale bar. **(Manual — do not automate.)**

- **Fig label:** `\label{fig:RES_IMU2}` (file: `RES_IMU2.0.png`)  
  **Problem:** Simulation trajectory on inclined terrain; slope angle experienced must be consistent with `fig:GRAPH_IMU2` pitch data.  
  **Action:** Cross-check pitch steady-state (~20°). Ensure axis labels and units present; font ≥ 10 pt. **(Manual.)**

- **Fig label:** `\label{fig:RES_IMU2_real}` (file: `RES_IMU2.0_real.png`)  
  **Problem:** Real-robot trajectory on inclined terrain; same consistency check as above.  
  **Action:** Confirm image matches 20° inclined test structure. Add scale bar; axis labels ≥ 10 pt. **(Manual.)**

- **Fig label:** `\label{fig:GRAPH_IMU2}` (file: `GRAPH_IMU2.png`)  
  **Problem:** Pitch angle time-series; steady-state pitch should match declared slope angle.  
  **Action:** Verify steady-state pitch ≈ 20°. Add axis labels ("Time (s)" / "Pitch (deg)"), units, threshold line, font ≥ 10 pt. **(Manual.)**

- **Fig label:** `\label{fig:GRAPH_IMU2_real}` (file: `GRAPH_IMU2_real.png`)  
  **Problem:** MLP outputs on inclined terrain; same slope-consistency check.  
  **Action:** Add axis labels, units, legend (N₀, N₁, N₂), font ≥ 10 pt. **(Manual.)**

#### B. Neural Raster-Plot Legibility — High Priority

For each figure below: regenerate at ≥ 300 DPI, add x-axis "Time (s)", y-axis "Neuron / Activity", sub-panel labels, legend where applicable, font ≥ 10 pt on all labels.

| Label | File | Action |
|-------|------|--------|
| `fig:NEU_EST_UNIG` | `NEU_EST_UNIG.png` | Add axes, sub-panel labels (a,b), scale bars |
| `fig:NEU_EST_UNIB` | `NEU_EST_UNIB.png` | Add axes, sub-panel labels (a,b), scale bars |
| `fig:NEU_EST_UNIG_real` | `NEU_EST_UNIG_real.png` | Add axes, sub-panel labels (a–c), scale bars |
| `fig:NEU_EST_MUL` | `NEU_EST_MUL.png` | Add axes, sub-panel labels (a–d), legend |
| `fig:NEU_EST_MUL_real` | `NEU_EST_MUL_real.png` | Add axes, sub-panel labels (a–d), legend |
| `fig:NEU_IMU` | `NEU_IMU.png` | Add axes, sub-panel labels (a,b) |
| `fig:NEU_IMU_real` | `NEU_IMU_real.png` | Add axes, sub-panel labels (a,b) |
| `fig:NEU_IMU2` | `NEU_IMU2.png` | Add axes, sub-panel labels (a,b) |
| `fig:NEU_IMU2_real` | `NEU_IMU2_real.png` | Add axes, sub-panel labels (a,b) |

#### C. General Figure Quality — Medium Priority

For **all** figures in the paper verify:

| Requirement | Specification |
|-------------|---------------|
| Axis label font | ≥ 10 pt (recommended 10–12 pt) |
| Tick label font | ≥ 8 pt |
| Axis units | Present on all quantitative axes |
| Legend | Present when > 1 curve/color is shown |
| Resolution | ≥ 300 DPI (raster); vector PDF/EPS preferred for plots |
| Scale bar | Add to all physical photographs (terrain, robot frames) where spatial scale is relevant |

- **`\label{fig:GRAPH_IMU}`** (`GRAPH_IMU.png`): Add x-axis "Time (s)", y-axis "σ_az (m/s²)", horizontal threshold line at 3.7.
- **`\label{fig:GRAPH_IMU_real}`** (`GRAPH_IMU_real.png`): Add x-axis, y-axis labels, legend for N₀, N₁, N₂.
- **`\label{fig:Terreno_irre}`** (`TERRENO_IRREGULAR.jpeg`): Add scale bar for 90 × 130 cm board and 3.6 cm max protrusion height.
- **Frame sequences D1–D6** (file: `D1.png`–`D6.png`): Add time stamps consistent with text (t = 0, …); confirm captions match actual frame order.
- **Frame sequences E1–E6** (file: `E1.png`–`E6.png`): Same as above; confirm 21-second interval between frames matches images.

> **Note on PDF figure numbers 3, 6, 33 (referenced in some reviewer comments):** The LaTeX file uses symbolic labels, not sequential numbers. To resolve figure-number references in reviewer comments, compile the manuscript and check the rendered numbering. Approximate correspondence based on `.tex` order: Fig. 3 may correspond to the Basal Ganglia diagram (`\label{fig:ganglios}`), Fig. 6 to the Gait Decision Module diagram (`\label{fig:Modos_Locomocion}`), and Fig. 33 to one of the inclined-terrain results figures. **Authors must confirm by inspection of the compiled PDF.**
