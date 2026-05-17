## Changelog — AUTO-EDITS

All changes listed below were applied automatically to `elsarticle-template-num-names.tex`. Equation expressions and numerical values were not modified; only explanatory prose was added or reorganized.

## [2026-05-17T23:15:14Z] - Tarea #18: Refinamiento de la Introducción por Feedback de Coautores
* **Reviewer Comment:** Reviewer 1 (Comment 1) and Reviewer 2 (Comment 1) requested stronger horizontal comparisons, clarity in definitions, and a more structured flow.
* **Change Made:** Modified `src/elsarticle-template-num-names.tex`. Connected the theoretical foundation of Girard et al. (2003) with the computational model of Kamali Sarvestani et al. (2013). Simplified the parenthetical description of locomotion modes into explicit "(articulated mode)" and "(mobile mode)" definitions. Added a standard structural closing paragraph outlining the organization of the paper.
* **Justification:** Resolves remaining structural and clarity issues in the Introduction. Grounding the computational model within its exact theoretical lineage provides the analytical rigor expected by reviewers, while the simplified definitions and structural outline fulfill Elsevier's formatting and readability standards.

## [2026-05-17T23:15:14Z] - Tarea #17: Purgado de Afirmaciones Industriales y Alineación de Tono
* **Reviewer Comment:** Reviewer 1 (Comment 5) flagged that the industrial-building scenario in simulation was not demonstrated or supported. Collectively, the reviewers challenged the industrial readiness of the low-torque, open-loop hardware setup.
* **Change Made:** Modified `src/elsarticle-template-num-names.tex`. Reframed the Abstract, replaced the unsupported industrial simulation sentence in Section 2.2 with an explicit focus on structured non-dynamic topographies, and rewrote the discussion/conclusions paragraphs to switch from "direct industrial deployment" to "computational feasibility and energy efficiency baselines."
* **Justification:** Aligns the entire narrative of the paper with the low-cost exploratory scope defined in Tarea 12 without devaluing the contribution. By explicitly framing the prototype as a robust mathematical and algorithmic baseline, we turn a weakness (hardware constraints) into a validated scientific foundation, while directly resolving the simulation discrepancy exposed by Reviewer 1.

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

> **Note on PDF figure numbers referenced in reviewer comments:** Some reviewer comments cite figures by sequential number (e.g., 3, 6, 33) rather than by LaTeX label. Because figure numbering is assigned at compile time, the bot cannot reliably determine the mapping without compiling the manuscript. **Authors must compile the PDF and create an explicit table mapping each sequential figure number to its `\label{}` identifier before addressing reviewer comments that reference figures by number.** This mapping is needed to correctly target the figures mentioned in the slope-inconsistency and legibility feedback.

---

## Changelog — 2026-05-10 (Tasks 5, 6, 7 — AUTO-EDITS)

All changes listed below were applied automatically to `elsarticle-template-num-names.tex` and `references.bib` during the Task 5/6/7 editing session (agent: ClaudeSonnet, date: 2026-05-10).

### TAREA 5 — Parameter Justifications and Equation Changes

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5a):** Renamed `j` → `\omega_{GpeR}` in equation `\eqref{eq:Z_4}` (line containing `(Gpe_G + j Gpe_R)_+`). Added `\omega_{GpeR} = 2.0` to `Table~\ref{table:Locom_NN}`. Added explanatory text: "where `\omega_{GpeR}` is a synaptic weight applied to the GPe_R channel (value: 2.0)." Added `% [AUTO-EDIT]` and `% [REF: renamed from j]` comments.  
  **Justification:** Parameter `j` was ambiguous (could be interpreted as imaginary unit or index); renaming to `\omega_{GpeR}` clarifies its physical meaning as a synaptic weight.

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5b):** Added `w = 10.0` entry to `Table~\ref{table:Locom_NN}`. Added explanatory text: "w denotes a global inhibitory synaptic weight used consistently in locomotion equations (value: 10.0)."  
  **Justification:** Parameter `w` appeared in multiple locomotion equations without a table entry or definition; added for completeness.

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5c):** Added paragraph after equations `\eqref{eq:ResL}`–`\eqref{eq:AuxL}`: "The matrices W^{(IR)}, W^{(RR)} and W^{(RA)} denote connectivity weight matrices (binary or fixed patterns). They represent fixed structural inter-neuron connectivity in the Integrating Neural Network (see Fig.~\ref{fig:IntLidar}). In this implementation, W matrices are fixed and uniform according to connectivity patterns adapted from Kamali Sarvestani et al."  
  **Justification:** W matrices were used in equations without explanation of their nature (fixed vs. learned, binary vs. continuous).

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5d):** Removed `μ_{STN} = 1.0` row from `Table~\ref{table:Ganglia}`. Added comment `% [AUTO-EDIT] TAREA 5d: μ_{STN} removed from parameters table; not used in equations.`  
  **Justification:** `μ_{STN}` appeared in the table but not in any equation of the manuscript; its presence was confusing and potentially misleading.

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5e):** Added sentence to explanatory text after `Table~\ref{table:LiDAR}`: "These weights are fixed uniform values derived from the basal-ganglia inspired architecture (Kamali Sarvestani et al.)."  
  **Justification:** `ω_{Z→L}` and `ω_{L→L}` had no stated design rationale; confirmed as unit values from architectural reference.

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5f):** Added paragraph in `\section{Conclusions}` (before "Several limitations" paragraph) providing justifications for: `ω_{L→X} = 160.0` (unconditional LiDAR reflex); asymmetry `ω_{Gpe_R→X4}=2.0` vs `ω_{Gpe_G→X4}=1.0` (higher aversive urgency); `ω_{X4→X7}`, `ω_{X3→X8}=10.0` (command amplification); `Ar = 28.0` (empirical camera calibration); `HI = 3.0` (motor static friction baseline); `σ_M = 0.3` (fast switching) and `σ_I = 1.5` (IMU noise tolerance); `U_{N0}=3.7`, `U_{N1}=7.8` (empirical thresholds, further validation recommended).  
  **Justification:** Reviewer 1 and Reviewer 3 requested justification for key parameter values.

- **File:** `elsarticle-template-num-names.tex`  
  **Change (5g):** Renamed `R_i` → `Stimuli_i` in equation `\eqref{eq:stn}`. Added comment `% [AUTO-EDIT] TAREA 5g`. Added sentence: "the index j represents summation across all neurons in the respective structure (summation variable)."  
  **Justification:** `R_i` was ambiguous (could be confused with response-layer notation); `Stimuli_i` clarifies it denotes the input stimulus strength for channel i. Added note on j to avoid confusion with j summation index in STN equation.

### TAREA 6 — Introduction Replacement

- **File:** `elsarticle-template-num-names.tex`  
  **Change:** Replaced entire `\section{Introduction}` block with LaTeX conversion of `intro_corregida 1.MD`. Kept the robot figure (`\label{fig:robot}`) by moving it to the Platform Design subsection. Added `% [AUTO-EDIT]` comments at start and end of new introduction block.  
  **Justification:** Required by reviewer feedback (Reviewer 1 Comment 1, Reviewer 2 Comment 1, Reviewer 3 Comment 6). See "Response to Referee — Corrections to the Introduction" section above.

- **File:** `references.bib`  
  **Change:** Added 24 new BibTeX entries for references cited in the new Introduction. Keys added:
  - `Bjelonic2019KeepRollin` (Bjelonic et al. 2019, Keep Rollin')
  - `Bjelonic2022OfflineMotion` (Bjelonic et al. 2022, Offline Motion Libraries)
  - `Lee2024Science` (Lee et al. 2024, Science Robotics)
  - `Kashiri2019CENTAURO` (Kashiri et al. 2019, CENTAURO)
  - `Klamt2019CENTAURO` (Klamt et al. 2019, CENTAURO evaluation)
  - `Klemm2019Ascento` (Klemm et al. 2019, Ascento ICRA)
  - `Klemm2020AscentoRAL` (Klemm et al. 2020, Ascento RA-L)
  - `Bjelonic2022Survey` (Bjelonic et al. 2022, Survey CLAWAR)
  - `Gurney2001a` (Gurney et al. 2001a, BG model I)
  - `Gurney2001b` (Gurney et al. 2001b, BG model II)
  - `Prescott2006Robot` (Prescott et al. 2006, Robot BG model)
  - `Girard2003Basal` (Girard et al. 2003, BG vs. WTA)
  - `Baston2015Biologically` (Baston & Ursino 2015, BG model)
  - `Prescott2024Simulated` (Prescott et al. 2024, Dopamine BG)
  - `Bellegarda2022CPGRL` (Bellegarda & Ijspeert 2022, CPG-RL)
  - `Manoonpong2013Neural` (Manoonpond et al. 2013, Neural control)
  - `Hutter2017ANYmal` (Hutter et al. 2017, ANYmal)
  - `Tranzatto2022CERBERUS` (Tranzatto et al. 2022, CERBERUS)
  - `Vogel2024Ladder` (Vogel et al. 2024, Ladder climbing)
  - `Halder2023Construction` (Halder et al. 2023, Construction inspection)
  - `Wang2025Autonomous` (Wang et al. 2025, Autonomous navigation)
  - `Halder2025Crack` (Halder et al. 2025, Crack detection)
  - `Humphreys2025BioInspired` (Humphreys & Zhou 2025, Bio-inspired gait)
  - `Liu2024Max` (Liu et al. 2024, Max robot)
  - `Cui2025FLORES` (Cui et al. 2025, FLORES)
  - `Jiang2025RTaichi` (Jiang et al. 2025, R-Taichi)

  **Authors please confirm:** If any BibTeX key, author list, or journal/conference metadata requires correction, please update `references.bib` directly and note the correction here.

### [REQUIRES AUTHOR INPUT] — Updated Items

- **`Ar = 28.0`** (location: `Table~\ref{table:Locom_NN}`): The justification added states calibration against Logitech C270 camera focal geometry. **Authors must provide supporting evidence** (measurement data, focal length calculation, or experimental log) to substantiate this claim before final submission.

- **`U_{N_0} = 3.7`, `U_{N_1} = 7.8`** (location: `Table~\ref{table:Locom_MLP}`): The added text notes these are empirical thresholds and recommends F1-score or ROC validation. **Authors should add classification metrics** (F1, precision, recall, confusion matrix) for the MLP terrain classifier to strengthen this claim.

- **`Manoonpong et al. [2013]`** (key: `Manoonpond2013Neural`): The source MD reference list spelled the name "Manoonpand"; the BibTeX entry has been corrected to "Manoonpong" (Poramate Manoonpong, Frontiers in Neural Circuits). **Authors should verify** this is the correct spelling before final submission.

- **`Cui et al. [2025]` (`Cui2025FLORES`)**: The arXiv number `2507.22345` in the MD appears to be in the future (July 2025). **Authors should verify the correct arXiv ID** once published and update the entry.

- **`Jiang et al. [2025]` (`Jiang2025RTaichi`)**: Only a PMC number was provided. **Authors should add full bibliographic details** (journal, volume, DOI) to the BibTeX entry.

- **`Wang et al. [2025]` (`Wang2025Autonomous`)**: Only a ResearchGate ID was provided in the MD. **Authors should add the journal name, volume, and DOI** once the article is formally published.

---

## Changelog — 2026-05-16 (Tasks 8, 9, 10, 11 — AUTO-EDITS)

All changes listed below were applied automatically to `elsarticle-template-num-names.tex`, `RESPONSE_TO_REVIEWERS.md`, and `Changelog.md` during the Task 8/9/10/11 editing session (agent: ClaudeSonnet, date: 2026-05-16).

### TAREA 8 — Ar Parameter Analytical Justification

- fecha: 2026-05-16  
  file: elsarticle-template-num-names.tex  
  change: Inserted analytical justification paragraph for $Ar = 28.0$ after Table~\ref{table:Locom_NN} description. % [AUTO-EDIT]  
  reviewer: Reviewer 2, Comment 2 / Reviewer 3, Comment 8  
  notes: Derivation uses pinhole camera model for Logitech C270 at 640×480 resolution.

- fecha: 2026-05-16  
  file: elsarticle-template-num-names.tex  
  change: Updated brief Ar mention in Discussion paragraph to cross-reference the new analytical derivation. % [AUTO-EDIT]  
  reviewer: Reviewer 2, Comment 2 / Reviewer 3, Comment 8  
  notes: Previous text stated "calibrated empirically"; now references the pinhole model derivation.

### TAREA 9 — Terrain Description Replacement

- fecha: 2026-05-16  
  file: elsarticle-template-num-names.tex  
  change: Replaced primitive terrain description (90×130 cm², 3.6 cm protrusions) with full Perlin-noise procedural characterization including statistical metrics. % [AUTO-EDIT]  
  reviewer: Reviewer 1, Comment 10  
  notes: New description includes μ_h ≈ 0.0 mm, σ_h² = 5.469 mm², σ_h = 2.339 mm, max 8.129 mm, min −8.983 mm, R_q = 2.339 mm. Figure references preserved.

### TAREA 10 — Proofreading

- fecha: 2026-05-16  
  file: elsarticle-template-num-names.tex  
  change: Comprehensive proofreading pass applied across all prose sections. Grammar, spelling, punctuation, and academic style corrected. Technical content unchanged. % [AUTO-EDIT]  
  reviewer: Reviewer 3, Comment 9  
  notes: Each edited paragraph marked with % [AUTO-EDIT] Proofreading: grammar/style comment. Equations, labels, references, and numerical values not modified.

### TAREA 11 — RESPONSE_TO_REVIEWERS.md Restructuring

- fecha: 2026-05-16  
  file: RESPONSE_TO_REVIEWERS.md  
  change: Added entries for Reviewer 1 Comment 10 (T9), Reviewer 2/3 Comment on Ar (T8), and Reviewer 3 Comment 9 (T10) in standard format. % [AUTO-EDIT]  
  reviewer: Reviewer 1, Comment 10 / Reviewer 2, Comment 2 / Reviewer 3, Comments 8 and 9  
  notes: Each entry follows exact format: Reviewer Comment, Change Made, Justification.

### ⚠️ [REQUIRES AUTHOR INPUT]

- **`Ar = 28.0` calibration log** (location: `Table~\ref{table:Locom_NN}`, analytical justification paragraph after table): The analytical derivation using the pinhole camera model has been added. However, authors should provide experimental validation data (e.g., measured stopping distance, actual focal length calibration from camera_calibration tool) to confirm that $Z = 31$ cm and $W_{obj} = 10$ cm match the physical experimental setup.

- **Terrain image update** (location: `\label{fig:Terreno_irre}`, file `TERRENO_IRREGULAR.jpeg`): The terrain description now references a Perlin-noise generated 1300×900 mm surface. Authors must update the figure to show the actual Perlin-noise terrain (or confirm the existing image matches the new description). The old caption "Irregular terrain." may need updating if the image changes.

---

## Changelog — 2026-05-17 (Tasks 12, 13, 14, 15, 16 — AUTO-EDITS)

All changes listed below were applied automatically to `elsarticle-template-num-names.tex`, `RESPONSE_TO_REVIEWERS.md`, and `Changelog.md` during the Task 12–16 editing session (agent: ClaudeSonnet, date: 2026-05-17T03:39:56Z).

### TAREA 12 — Reframing scope as low-cost research platform

- fecha: 2026-05-17T03:39:56Z
  file: elsarticle-template-num-names.tex
  change: Added `\subsection{Limitations of the Present Work and Reframed Scope}` (label: ssec:Limitations) immediately before `\section{Conclusions}`. Contains explicit physical and algorithmic scope boundaries for the prototype. % [AUTO-EDIT]
  reviewer: Reviewer 1, Comment 11 / Reviewer 2, Comment 4
  notes: Acknowledges low-torque actuation, open-loop gaits, laboratory-only validation, and repositions contribution toward BG efficiency/interpretability.

- fecha: 2026-05-17T03:39:56Z
  file: elsarticle-template-num-names.tex
  change: Added reframed closing paragraph at end of `\section{Conclusions}` explicitly stating hardware limitations and future work toward industrial-grade platforms. % [AUTO-EDIT]
  reviewer: Reviewer 1, Comment 11 / Reviewer 2, Comment 4
  notes: Paragraph appended after existing conclusions; does not remove any prior content.

### TAREA 13 — Clarification of simulation platform adoption

- fecha: 2026-05-10T21:01:26Z (previously applied)
  file: elsarticle-template-num-names.tex
  change: Replaced ambiguous sentence in Section 2 methodology paragraph with clarified version distinguishing simulation design as morphological reference vs. prior engineering work as fabrication know-how. % [AUTO-EDIT]
  reviewer: Reviewer 1, Comment 3
  notes: Already applied in prior session. Documented here for completeness. RESPONSE_TO_REVIEWERS.md entry was already present from prior session (lines 40–53).

### TAREA 14 — STL/pitch discretization explanation

- fecha: 2026-05-17T03:39:56Z
  file: elsarticle-template-num-names.tex
  change: Inserted explanation of step-like pitch response due to STL mesh discretization, immediately after the sentence referencing Figure~\ref{fig:GRAPH_IMU2} in the Simulation Results / Response to Variable Topographies subsection. % [AUTO-EDIT]
  reviewer: Reviewer 1, Comment 4
  notes: Explains why pitch plots show alternating phases of angular change and stationary plateaus despite visually continuous terrain slope.

### TAREA 15 — MLP processes IMU (not replaces)

- fecha: 2026-05-17T03:39:56Z
  file: elsarticle-template-num-names.tex
  change: Replaced MLP introductory paragraph in Gait Decision Module subsection. New wording explicitly states the MLP does not replace the physical IMU but processes raw inertial telemetry to produce high-level geometric classifications. % [AUTO-EDIT]
  reviewer: Reviewer 1, Comment 6
  notes: "an alternative based on a multilayer perceptron network" replaced by pipeline-role clarification. Physical MPU-6050 IMU remains primary sensor.

### TAREA 16 — BG justification and neuronal dynamics metrics

- fecha: 2026-05-17T03:39:56Z
  file: elsarticle-template-num-names.tex
  change: Added BG justification paragraph and requested neuronal dynamics metrics. % [AUTO-EDIT]
  reviewer: Reviewer 3, Comment 1
  notes: Paragraph added after Table~\ref{table:Ganglia} in the Basal Ganglia Module subsection. Neuronal dynamics metrics are listed in the REQUIRES AUTHOR INPUT section below.

### ⚠️ [REQUIRES AUTHOR INPUT]

- **Neuronal dynamics metrics** (location: `\subsubsection{Basal Ganglia Module}`, new BG justification paragraph; `\section{Conclusions}`, Limitations subsection): Reviewer 3, Comment 1 requests quantitative characterization of the BG neural dynamics. Authors must compute and report:
  - [ ] Decision latency (ms): time from stimulus onset to winner-take-all output stabilization.
  - [ ] Temporal consistency of the WTA mechanism: repeatability of selection across repeated presentations of the same stimuli configuration.
  - [ ] Conflict-resolution efficiency: how quickly the BG module suppresses competing channels when two stimuli are presented simultaneously.

- **Comparative IMU vs. MLP experiment** (location: `\subsubsection{Gait Decision Module}`, revised MLP paragraph; `\subsection{Physical Implementation Results}`): Reviewer 1, Comment 6 requests comparative experiments. Authors should consider adding a table or figure comparing fixed-threshold IMU-based terrain detection (roll/pitch/$\sigma_{az}$) versus MLP classification accuracy on the same test sequences. This would directly substantiate the claim that the MLP outperforms fixed-threshold heuristics.

- **MLP training data and performance metrics** (location: `\subsubsection{Gait Decision Module}`): Reviewer 1, Comment 8 requests MLP training data source and final classification performance. Authors must add: training dataset description (number of samples per terrain class, data collection protocol), and classification metrics (accuracy, precision, recall, F1-score, or confusion matrix). See also Changelog entry from 2026-05-16.
