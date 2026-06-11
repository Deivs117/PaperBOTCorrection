# PROMPT DE REVISIÓN EDITORIAL CRÍTICA
## Para: Agente Corrector de LaTeX
## Documento objetivo: `src/elsarticle-template-num-names.tex`
## Fecha de revisión: 2026-06-11
## Rol requerido: Editor Senior Q1 / Elsevier / Robotics and Autonomous Systems

---

Este documento contiene todas las observaciones, errores, inconsistencias y problemas de redacción detectados en el manuscrito. El agente receptor debe leer cada ítem, localizar la línea indicada en el archivo `.tex`, y aplicar la corrección correspondiente. Después de cada corrección al `.tex`, debe actualizar `Changelog.md` y `RESPONSE_TO_REVIEWERS.md` según lo establecido en `AGENTS.MD`.

---

## CATEGORÍA A — ERRORES ESTRUCTURALES GRAVES (PRIORIDAD CRÍTICA)

### A1. Contradicción entre la hoja de ruta de la Introducción y la estructura real del artículo
**Línea:** 133
**Problema:** La introducción afirma: *"Section 4 discusses the algorithmic efficiency, novelty, and physical boundaries of the platform. Finally, Section 5 outlines the conclusions and directions for future work."* Sin embargo, en el documento real **no existe una Sección 4 de Discussion** independiente. El documento pasa directamente de la Sección 3 (Results) a una Sección 4 titulada `\section{Conclusions}`. La hoja de ruta anuncia 5 secciones pero el artículo tiene 4. Esta contradicción engaña al lector y a los revisores.
**Corrección requerida:** Actualizar el párrafo final de la Introducción (línea 133) para reflejar la estructura real del artículo: *"...Section~3 presents the experimental results...Section~4 presents the discussion and conclusions..."*, o bien añadir la `\section{Discussion}` faltante antes de `\section{Conclusions}`.

---

### A2. Duplicación masiva de filas en la Tabla de parámetros de la red de locomoción
**Líneas:** 409–460 (`table:Locom_NN`)
**Problema:** La tabla tiene múltiples filas duplicadas. Los siguientes parámetros aparecen **dos veces cada uno**:
- `$\omega_{Gpe_G \rightarrow X_4}$` = 1.0 (líneas 417 y 429)
- `$\omega_{Gpe_R \rightarrow X_4}$` = 2.0 (líneas 418 y 430)
- `$\omega_{L \rightarrow X}$` = 160.0 (líneas 420 y 432)
- `$\omega_{X_3 \rightarrow X_7}$` = 1.0 (líneas 422 y 436)
- `$\omega_{X_4 \rightarrow X_7}$` = 10.0 (líneas 423 y 437)
- `$\omega_{X_5 \rightarrow X_7}$` = 1.0 (líneas 424 y 438)
- `$\omega_{X_3 \rightarrow X_8}$` = 10.0 (líneas 425 y 440)
**Corrección requerida:** Eliminar el bloque duplicado (aproximadamente líneas 428–441). La tabla debe listar cada parámetro exactamente una vez.

---

### A3. Número de figura codificado manualmente (hardcoded)
**Línea:** 1586
**Problema:** El texto dice `(Figure~33)` con un número hardcoded. En un documento LaTeX, los números de figura deben referenciarse siempre con `\ref{label}`, no como literales. Si las figuras se reordenan, este número quedará incorrecto sin aviso.
**Corrección requerida:** Identificar a qué figura se refiere este pasaje (aparentemente es la figura del robot escalando la rampa empinada) y reemplazar `Figure~33` por `Figure~\ref{<etiqueta_correcta>}`.

---

### A4. Inconsistencia crítica en la asignación de modos de locomoción a unidades neuronales
**Líneas:** 199–200, 483–484, 722–725, 826–827
**Problema:** El manuscrito es inconsistente sobre qué unidad neuronal ($X_{14}$, $X_{15}$, $X_{16}$) activa qué modo de locomoción. Concretamente:

- La **Metodología** (líneas 199–200 y 483–484) establece:
  - Estímulo apetitivo → **modo rolling diferencial**
  - Estímulo aversivo → **modo cuadrúpedo**
  - Obstáculo → **modo omnidireccional**

- Los **Resultados, experimento de estímulo único** (líneas 722–725) dicen:
  - Obstáculo → `$X_{14}$` = "omnidirectional gait" ✓
  - Estímulo apetitivo → `$X_{15}$` = "**quadrupedal gait**" ✗ ← **debería ser rolling diferencial**

- Los **Resultados, estímulos múltiples** (línea 826–827) dicen: "progressive neuronal activities of units $X_{16}$, $X_{14}$, and $X_{15}$ in that order" para la secuencia obstáculo→aversivo→apetitivo. Si X_{14}=omnidireccional (como establece la línea 722), entonces X_{16} y X_{14} serían omnidireccionales en distintos momentos — otra contradicción.

**Corrección requerida:** Verificar con el equipo de autores cuál es el mapeo correcto de $X_{14}$/$X_{15}$/$X_{16}$ a modos de locomoción. La palabra "quadrupedal gait" en la línea 725 parece ser un error tipográfico; debería decir "differential rolling mode". Además, revisar la consistencia de la secuencia en la línea 826.

---

### A5. Etiqueta duplicada en tabla
**Líneas:** 551 y 561
**Problema:** La tabla de codificación de movimiento tiene **dos comandos `\label`**:
```latex
\label{tab:dir-bits}   % línea 551
...
\label{table:DIR_BINARY}   % línea 561
```
Dos `\label` en el mismo entorno generan una advertencia de etiqueta duplicada y comportamiento indefinido en las referencias.
**Corrección requerida:** Eliminar una de las dos etiquetas. En el cuerpo del texto (línea 545) se referencia `\ref{table:DIR_BINARY}`, por lo tanto conservar `\label{table:DIR_BINARY}` y eliminar `\label{tab:dir-bits}`.

---

## CATEGORÍA B — INCONSISTENCIAS TERMINOLÓGICAS

### B1. "Aversive" vs "Adversive" vs "Adversarial" — término incorrecto
**Líneas:** 644 y 1244
**Problema:** El término técnico establecido y usado de manera consistente en todo el manuscrito es **"aversive"** (estímulo aversivo). Sin embargo:
- Línea 644 (subfigure caption): `\caption{Adversarial stimulus}` — debe ser "Aversive stimulus"
- Línea 1244 (subfigure caption): `\caption{Frame 4 - Adversive stimuli evasion.}` — "Adversive" no es una palabra en inglés; debe ser "Aversive stimulus evasion."

---

### B2. Terminología inconsistente para los modos de locomoción
**Problema:** El mismo modo de locomoción recibe nombres distintos a lo largo del artículo sin aclarar que son sinónimos:
- "Differential rolling mode" / "differential-drive rolling mode" / "H-mode" / "differential rolling" / "Differential Mobile Mode"
- "Omnidirectional mode" / "omnidirectional motion" / "omnidirectional gait"
- "Quadrupedal mode" / "quadrupedal walking" / "articulated mode" / "C-mode"

**Corrección requerida:** Definir formalmente los tres nombres canónicos al primer uso en la Sección 2 (por ejemplo, en la introducción de la Subsección de Diseño) y usarlos consistentemente. Los alias (H-mode, C-mode) deben introducirse entre paréntesis solo una vez.

---

### B3. Uso inconsistente de "agent" vs "robot" vs "platform"
**Líneas:** 722, 724, 725
**Problema:** En la Sección de Resultados se usa el término "agent" de forma aislada ("the agent's right side", "The agent approaches"), mientras que el resto del documento usa "robot" o "platform". "Agent" no está definido previamente y su aparición aislada en el contexto de resultados físicos es confusa.
**Corrección requerida:** Reemplazar "agent" por "robot" o "platform" en estas líneas para mantener consistencia terminológica.

---

### B4. Uso inconsistente de ortografía americana vs británica
**Líneas:** 680 y otras
**Problema:** El artículo mezcla ortografía americana y británica. Ejemplos detectados:
- "contextualise" (línea 680) — debe ser "contextualize" (Am.)
- "behaviours" (en varios `\revblue{}` blocks) — debe ser "behaviors" (Am.)
- La revista *Robotics and Autonomous Systems* (Elsevier) generalmente acepta ambas, pero el artículo debe ser **internamente consistente**.
**Corrección requerida:** Elegir una variante (se recomienda American English, consistente con la mayoría del documento) y unificar todas las ocurrencias.

---

## CATEGORÍA C — ERRORES GRAMATICALES Y DE REDACCIÓN

### C1. "In the incoming equations" — uso incorrecto del adjetivo
**Línea:** 274
**Problema:** "In the incoming equations, the subscript..." — "incoming" no es la palabra correcta en este contexto académico. Significa "que llegan/entrantes" y no describe ecuaciones presentadas a continuación.
**Corrección requerida:** Reemplazar por "In the following equations" o "In the equations below".

---

### C2. Punto antes de tilde en referencia de ecuación
**Línea:** 352
**Problema:** `"This is shown in Equations.~\eqref{eq:Z_5} and \eqref{eq:Z_6}"` — el punto después de "Equations" es incorrecto; crea una interrupción de oración antes de la referencia.
**Corrección requerida:** Cambiar a `"This is shown in Equations~\eqref{eq:Z_5} and~\eqref{eq:Z_6}"`.

---

### C3. Estructura de oración rota alrededor de las referencias de ecuaciones Naka–Rushton
**Línea:** 494
**Problema:** `"Specifically, $f_{\mathrm{Imu}}(\cdot)$ and $f_{\mathrm{Mode}}(\cdot)$ Equations~\eqref{eq:NakaImu} and \eqref{eq:NakaMode},share the same second-order Naka--Rushton structure"` — Las referencias de ecuación están insertadas dentro de la oración de forma que la rompen gramaticalmente. Además falta espacio después de la coma: `,share` debe ser `, share`.
**Corrección requerida:** Reestructurar a: `"Specifically, $f_{\mathrm{Imu}}(\cdot)$ and $f_{\mathrm{Mode}}(\cdot)$ (Equations~\eqref{eq:NakaImu} and~\eqref{eq:NakaMode}) share the same second-order Naka--Rushton structure, but use different..."`.

---

### C4. Guiones cortos usados como guiones largos (em-dash)
**Línea:** 904
**Problema:** `"neuron $X_{1}$-associated with detecting an inclination greater than five degrees-excites unit $X_{15}$"` — Los guiones simples `-` se usan aquí como em-dashes para un inciso. El estándar del documento usa `---`.
**Corrección requerida:** Reemplazar por `"neuron $X_{1}$---associated with detecting an inclination greater than five degrees---excites unit $X_{15}$"` o usar paréntesis: `"neuron $X_{1}$ (associated with detecting an inclination greater than five degrees) excites unit $X_{15}$"`.

---

### C5. Espacio faltante antes de paréntesis en textos de resultados cuantitativos
**Líneas:** 755, 776, 797
**Problema:** `"Appetitive Targeting(See Figure \ref{fig:appetitive_results}):"` — Falta espacio entre el nombre de la prueba y el paréntesis que contiene la referencia. Mismo error en las líneas 776 y 797.
**Corrección requerida:**
- Línea 755: `"Appetitive Targeting (see Figure~\ref{fig:appetitive_results}):"` (minúscula en "see" dentro del paréntesis, y añadir `~` no-break space antes de `\ref`)
- Línea 776: `"Aversive Escape (see Figure~\ref{fig:aversive_results}):"`
- Línea 797: `"Obstacle Evasion (see Figure~\ref{fig:obstacle_results}):"`

---

### C6. "The robot experiences a stagnation state" — antropomorfismo inadecuado
**Línea:** 1327
**Problema:** `"the robot experiences a stagnation state"` — "experiences" es una atribución de experiencia subjetiva a un sistema mecánico. Esta redacción no es apropiada en un artículo técnico Q1.
**Corrección requerida:** Reemplazar por `"a stagnation condition is detected"` o `"the stagnation signal reaches its maximum sustained amplitude"`.

---

### C7. Cambios de tiempo verbal en la Metodología (presente vs pasado pasivo)
**Líneas:** 199–207
**Problema:** La Sección de Metodología mezcla tiempo verbal. Según las directrices de AGENTS.MD, la metodología debe usar voz pasiva en tiempo pasado para describir experimentos y diseño. Se detectan inconsistencias:
- Línea 199: "Three principal behaviors **were** defined" ✓ — pero a continuación: "the robot **advances** using differential rolling mode" (presente activo) ✗
- Línea 207: "a visual input **was** implemented through a camera, which **provides** information" — cambio de pasado a presente en la misma oración ✗
- Línea 210: "The sensory ring **is** composed of 16 units" (presente) — debería ser "**was** composed" o "**comprised**" ✗

**Corrección requerida:** Estandarizar la Sección 2 al pasado pasivo: "the robot **advanced** using differential rolling mode", "which **provided** information", "The sensory ring **comprised** 16 units".

---

### C8. Repetición de contenido — descripción duplicada del anillo de neuronas
**Líneas:** 209 y 211
**Problema:** El texto contiene una repetición casi exacta en dos párrafos consecutivos:
- Línea 209: `"The ring consists of 16 units, each responding with maximal amplitude to a preferred angle, indicating the direction in which the obstacle is located."`
- Línea 211: `"The sensory ring is composed of 16 units, each exhibiting a maximal response toward a preferred angle, thus indicating the direction of the detected obstacle."`

Ambas oraciones dicen lo mismo. Esta redundancia debe eliminarse.
**Corrección requerida:** Eliminar la segunda aparición (línea 211, primera oración) y mantener solo la primera, integrando el contenido adicional del resto del párrafo de la línea 211.

---

### C9. "The obtained results are consistent with..." — referencia informal sin citación LaTeX
**Línea:** 1616
**Problema:** `"The obtained results are consistent with those reported by Sarvestani et al., who demonstrated..."` — (1) "The obtained results" es una locución débil para introducir una comparación con la literatura; debe ser "These results are consistent with..." o "The present findings align with...". (2) "Sarvestani et al." debe usar la macro de citación `\citet{sarvestani2013computational}` en lugar de texto plano.
**Corrección requerida:** Cambiar a `"These results are consistent with those reported by \citet{sarvestani2013computational}, who demonstrated..."`.

---

### C10. "Evidencing" — no estándar en inglés académico Q1
**Línea:** 1625
**Problema:** `"evidencing a solid computational foundation"` — "evidencing" como gerundio transitivo es infrecuente y no estándar en publicaciones Q1 de ingeniería. El equivalente correcto es "demonstrating".
**Corrección requerida:** Reemplazar por `"demonstrating a solid computational foundation"`.

---

### C11. "In an average time under 80 seconds" — preposición incorrecta
**Línea:** 1608
**Problema:** `"in an average time under 80 seconds"` — La preposición "under" es informal en este contexto. En inglés académico formal se prefiere "below" o "of less than".
**Corrección requerida:** Cambiar a `"in an average time of less than 80~s"`.

---

### C12. "Direction-switching latencies under 600 ms" — misma preposición informal
**Línea:** 1612
**Problema:** `"direction-switching latencies under 600 ms"` — mismo problema que C11.
**Corrección requerida:** Cambiar a `"direction-switching latencies below 600~ms"`.

---

### C13. "Bounded below $60$~s" — ambigüedad matemática
**Línea:** 851
**Problema:** `"completion times bounded below $60$~s"` — La expresión es ambigua: "bounded below" significa matemáticamente que hay un límite inferior. Se quiere decir que los tiempos se mantienen por debajo de 60 s, lo cual sería "bounded above by $60$~s" o simplemente "remaining below $60$~s".
**Corrección requerida:** Cambiar a `"completion times remaining below $60$~s"`.

---

### C14. "Performance metrics from all four experimental simulation" — error gramatical
**Línea:** 855
**Problema:** `"performance metrics from all four experimental simulation"` — falta la "s" en "simulation**s**". Además, "multi stimulus" debe llevar guión: "multi-stimulus".
**Corrección requerida:** Cambiar a `"performance metrics from all four experimental simulations, in both single- and multi-stimulus scenarios"`.

---

## CATEGORÍA D — PROBLEMAS EN LEYENDAS DE FIGURAS

### D1. Caption de figura con texto excesivamente largo e informal
**Línea:** 815–816
**Problema:** La leyenda de `fig:RES_EST_MUL` es demasiado larga e informal para una publicación Q1: `"Path followed before different stimuli in a simulation trial. The capture times are at the first moment, at 8 seconds, 15 seconds, 20 seconds, 25 seconds, and from 40 seconds onwards, positions were taken every 35 seconds until the simulation ended in 3 minutes."` — (1) "before different stimuli" debería ser "in response to multiple stimuli". (2) El desglose temporal en la leyenda es innecesariamente detallado.
**Corrección requerida:** Simplificar a: `"Trajectory followed in response to multiple stimuli of different natures in a simulation trial. Snapshots captured at selected time instants (0, 8, 15, 20, 25, and every 35~s thereafter until 3~min)."`.

---

### D2. Caption de figura: "Physical robot built" — redacción pobre
**Línea:** 629
**Problema:** `"Physical robot built."` — Esta frase es una caption extremadamente pobre. No identifica la plataforma ni aporta contexto.
**Corrección requerida:** Cambiar a `"Assembled physical robotic platform."` o `"Photograph of the fully assembled quadrupedal robotic prototype."`.

---

### D3. Captions repetitivas con redacción idéntica para figuras de simulación y físicas
**Líneas:** 893, 913, 1379, 1402
**Problema:** Las captions de figuras de respuesta neuronal usan frases torpes como "Neuronal response **for transport** on an unstable terrain" y "Neuronal response **for transport** in a terrain with elevation". La preposición "for transport" no es idiomática en inglés académico.
**Corrección requerida:**
- Línea 893: `"Neural activations during locomotion over irregular terrain (simulation). (a)~Locomotion decision module; (b)~Gait mode control module."`
- Línea 913: `"Neural activations during locomotion over inclined terrain (simulation). (a)~Locomotion decision module; (b)~Gait mode control module."`
- Línea 1379: `"Neural activations during locomotion over irregular terrain (physical robot). (a)~Locomotion decision module; (b)~Gait mode control module."`
- Línea 1402: `"Neural activations during locomotion over inclined terrain (physical robot). (a)~Locomotion decision module; (b)~Gait mode control module."`

---

### D4. Caption "Trajectory accomplished for transport in a terrain with elevation" — redacción pobre
**Línea:** 920
**Problema:** `"Trajectory accomplished for transport in a terrain with elevation during a simulation trial."` — "Trajectory accomplished for transport" es una construcción gramaticalmente torpe.
**Corrección requerida:** Cambiar a `"Trajectory during traversal of elevated terrain in simulation. Snapshots taken every 12~s."`.

---

### D5. Caption con coma faltante y redacción inconsistente
**Línea:** 302
**Problema:** `"Basal Ganglia Module. Structure proposed after \citet{sarvestani2013computational}"` — Falta un punto al final de la oración.
**Corrección requerida:** Añadir punto: `"Basal Ganglia Module. Structure proposed after \citet{sarvestani2013computational}."`.

---

### D6. Caption con inconsistencia entre estimulo "apetente" en imagen vs texto
**Línea:** 639 vs 183
**Problema:** Las figuras de estímulo apetitivo muestran captions "Appetitive stimulus" consistentes tanto en simulación (línea 185) como en el robot real (línea 639). Sin embargo, la caption de la figura de estímulo aversivo en el robot real (línea 644) dice `"Adversarial stimulus"` en lugar de `"Aversive stimulus"`. También, las figuras de estímulo en el entorno simulado tienen la etiqueta `\label{fig:estímulos}` con tilde — funciona en LaTeX moderno pero es una práctica no recomendada.
**Corrección requerida:** (1) Cambiar `"Adversarial stimulus"` → `"Aversive stimulus"` en línea 644. (2) Reemplazar los labels con tildes: `fig:estímulos` → `fig:estimulos` y `fig:estímulos_reales` → `fig:estimulos_reales`, actualizando todas las referencias `\ref{}` correspondientes.

---

### D7. Uso de `\captionof` dentro de entorno `figure`
**Líneas:** 709, 1181
**Problema:** Se usa `\captionof{figure}{...}` dentro de un entorno `\begin{figure}`. Dentro de un entorno `figure`, el comando correcto es simplemente `\caption{...}`. Usar `\captionof` es correcto solo fuera de entornos flotantes (e.g., dentro de `minipage`). Aunque funciona por razones de implementación, es redundante e inadecuado estilísticamente.
**Corrección requerida:** Cambiar `\captionof{figure}{...}` → `\caption{...}` en ambas líneas.

---

## CATEGORÍA E — INCONSISTENCIAS EN ECUACIONES Y DEFINICIONES

### E1. Índice no ligado en la ecuación de la capa de entrada
**Línea:** 281 (`eq:InputL`)
**Problema:** La ecuación dice:
```latex
\frac{d\, I_n}{dt} = \frac{1}{\tau_{IRA}} \left( -I_n + Z_i \right)
```
El índice `i` en `Z_i` no está ligado por ninguna suma ni especificación. Si el sistema tiene N=16 neuronas de anillo, no está claro cuál `Z_i` alimenta a `I_n`. En los sistemas de este tipo, cada neurona de entrada recibe su correspondiente señal del anillo, por lo que debería ser `Z_n` (el n-ésimo elemento) o podría requerir una aclaración explícita.
**Corrección requerida:** Preguntar a los autores si la ecuación correcta es `Z_n` (correspondencia uno-a-uno) o `\sum_i W_{n,i} Z_i` (conexión ponderada). Registrar como pendiente en la sección `[REQUIRES AUTHOR INPUT]` de `Changelog.md` si no se puede determinar de los apuntes disponibles.

---

### E2. Inconsistencia: N_0 y N_1 descritos como binarios cuando son probabilidades
**Línea:** 877
**Problema:** La línea 877 dice: `"this information corresponds to the MLP outputs $N_{0}$, $N_{1}$, and $N_{2}$, which implement binary outputs to represent the different terrain states."` Pero la línea 571 establece claramente que `"Output neurons $N_0$ and $N_1$ represent the **probability** of the terrain being flat or inclined"`, y solo `N_2` es binario. Decir que N_0 y N_1 "implement binary outputs" es factualmente incorrecto.
**Corrección requerida:** Cambiar la línea 877 a: `"this information corresponds to the MLP outputs: $N_{0}$ (flat-terrain probability), $N_{1}$ (inclined-terrain probability), and $N_{2}$ (binary stagnation indicator)."`.

---

### E3. Inconsistencia en la descripción del modo de gait para estímulo apetitivo
**Referencia cruzada con A4**
**Línea:** 725
**Problema adicional de redacción:** La frase `"the locomotion-mode module shows activation of unit $X_{15}$, responsible for enabling quadrupedal gait"` en el contexto del estímulo apetitivo contradice la regla de diseño definida en la Metodología.
**Corrección propuesta:** Basado en el análisis del sistema de ecuaciones (z_{15} en las ecuaciones 520-527 es inhibido por la señal apetitiva G_{pe,y}), es probable que la palabra "quadrupedal" sea un error tipográfico y debería decir "**differential rolling mode**". Solicitar confirmación a los autores.

---

## CATEGORÍA F — PROBLEMAS EN EL HIGHLIGHTS Y ABSTRACT

### F1. Highlight #4 sin punto final y redacción excesivamente larga
**Línea:** 97
**Problema:** El cuarto highlight dice: `"The robot system switches among rolling, quadrupedal, and omnidirectional modes, depending on the incoming stimuli and the specific characteristics of the environment"` — (1) Falta punto al final. (2) Es notablemente más largo que los otros highlights, rompiendo el paralelismo de la sección.
**Corrección requerida:** Acortar y añadir punto: `"The controller switches adaptively among rolling, quadrupedal, and omnidirectional modes in response to sensory context."`.

---

### F2. Marcado `\revblue{}` visible en el Abstract
**Línea:** 84
**Problema:** El Abstract contiene el comando `\revblue{...}` que genera texto en azul para rastreo de revisiones. El Abstract es uno de los primeros elementos que ven los editores y el texto en azul en él podría considerarse inapropiado para la versión final.
**Nota:** Este es un problema de presentación. Si el artículo está en fase de revisión/rebuttal, el markup es aceptable. Sin embargo, verificar con los autores si el Abstract debe presentarse limpio o con markup de revisión.

---

## CATEGORÍA G — POSICIÓN ESTRUCTURAL INADECUADA DE CONTENIDO

### G1. Justificaciones de parámetros de diseño al final de las Conclusiones
**Líneas:** 1620–1622
**Problema:** Un párrafo largo que justifica los valores numéricos de los parámetros de diseño (`\omega_{L\rightarrow X} = 160.0`, `\omega_{GpeR}`, `Ar = 28.0`, `HI`, `\sigma_M`, `\sigma_I`) aparece al **final de la sección de Conclusiones**, después de los comentarios de cierre del artículo. Las justificaciones de parámetros pertenecen a la **Sección de Metodología**, no a las Conclusiones.
**Corrección requerida:** Mover este bloque de texto (líneas 1620–1622) al final de la Subsección `Gait Decision Module` (Section 2.3.4), justo después de la Tabla `table:Locom_NN`, donde ya existe una justificación parcial del parámetro `Ar`.

---

### G2. Subsección de Limitaciones ubicada dentro de Resultados
**Línea:** 1583
**Problema:** `\subsection{\revblue{Limitations of the Present Work}}` aparece como una subsección de la Sección de Resultados (Section 3). Las Limitaciones son típicamente parte de la Discusión o las Conclusiones, no de los Resultados.
**Corrección requerida:** Mover la subsección de Limitaciones para que sea una subsección de las Conclusiones, o crear la Sección 4 (Discussion) que se menciona en la hoja de ruta de la Introducción, y colocarla allí (ver también ítem A1).

---

## CATEGORÍA H — PROBLEMAS MENORES DE REDACCIÓN Y FORMATO

### H1. Descripción informal del tiempo en resultados
**Líneas:** 821, 825
**Problema:** `"At second 21, the neuronal responses..."` y `"at second 27"` — El uso de "At second N" es coloquial. En redacción técnica se prefiere `"At $t = 21$~s"` o `"At 21~s into the experiment"`.
**Corrección requerida:**
- Línea 821: `"At $t = 21$~s, the neuronal responses..."`
- Línea 825: `"at $t = 27$~s"`

---

### H2. "By employing a smooth capsule geometry" — referente ambiguo
**Línea:** 797
**Problema:** `"By employing a smooth capsule geometry, the platform significantly optimizes physical interaction profiles, preventing localized torque spikes."` — "capsule geometry" parece referirse a la geometría del **obstáculo**, no de la plataforma. Este referente es confuso: ¿es el obstáculo el que tiene geometría de cápsula, o la plataforma? Además, "optimizes" debería estar en tiempo pasado ("optimized") si la Metodología se describe en pasado.
**Corrección requerida:** Aclarar el referente: `"By adopting obstacles with smooth capsule geometries in simulation, localized torque spikes during contact were prevented..."`. Registrar como pendiente en `[REQUIRES AUTHOR INPUT]` si los autores deben confirmar el referente.

---

### H3. Párrafo excesivamente largo en sección de resultados cuantitativos de estabilidad
**Línea:** 960–964
**Problema:** Los párrafos de análisis de resultados de topografías variables (líneas 960–964) son extraordinariamente largos y están fragmentados por el markup `\revblue{}` intercalado entre palabras individuales, lo que produce texto difícil de leer. Por ejemplo: `"The $TR$ \revblue{metric was formally derived from...} $TR = 1 - SM/r_{in}$\revblue{, where} $SM$..."`. Este estilo de markup fragmentado es correcto para tracking de cambios, pero el texto subyacente también tiene problemas de longitud.
**Recomendación:** Dividir el párrafo de la línea 960 en al menos dos párrafos: uno sobre la métrica TR y otro sobre los resultados cuantitativos. Si este texto se aprueba para versión final, consolidar los `\revblue{}` para que envuelvan oraciones completas en lugar de fragmentos.

---

### H4. Título de subsección no idiomático
**Línea:** 615
**Problema:** `"Robot Construction Materials and Testing Space"` es un título de subsección inusualmente literal. En un artículo Q1 el estándar sería algo como `"Physical Platform Construction and Experimental Setup"` o `"Hardware Implementation and Experimental Facilities"`.
**Corrección requerida:** Cambiar a `"Physical Platform Construction and Experimental Setup"`.

---

### H5. Referencias de raster plot inconsistentes entre secciones
**Líneas:** 719, 729, 808, 1191, 1209
**Problema:** Las figuras de actividad neuronal usan dos términos intercambiables como prefijo en sus captions: "Rastergram" (líneas 719, 729, 1191, 1209) y "Raster plot" (línea 808). Deben ser consistentes.
**Corrección requerida:** Elegir un término único. "Raster plot" o "Neural activation raster" son los términos más comunes en neurociencia computacional. Reemplazar todas las ocurrencias de "Rastergram" por "Raster plot of neural activations" o simplemente "Neural activation raster".

---

## CATEGORÍA I — NOTAS PARA LOS AUTORES (REQUIRES AUTHOR INPUT)

Los siguientes ítems no pueden ser resueltos por el agente corrector sin confirmación de los autores y deben ser registrados en `Changelog.md` bajo la sección `## ⚠️ [REQUIRES AUTHOR INPUT]`:

1. **[A1] Estructura de secciones:** ¿Se debe agregar una Sección 4 de Discussion separada, o actualizar la hoja de ruta de la Introducción para reflejar la estructura actual de 4 secciones?

2. **[A4 / E3] Mapeo X_{14}/X_{15}/X_{16} → modos de locomoción:** Confirmar el mapeo correcto. La línea 725 parece contener un error tipográfico ("quadrupedal" para estímulo apetitivo). ¿Cuál es la asignación correcta?

3. **[E1] Ecuación InputL (línea 281):** ¿El índice en `Z_i` debe ser `Z_n` (correspondencia uno-a-uno) o una suma ponderada?

4. **[H2] "Smooth capsule geometry":** ¿Se refiere a la geometría del obstáculo o de la plataforma? Aclarar el referente.

5. **[A3] Figure~33 (línea 1586):** Identificar la etiqueta LaTeX correcta para reemplazar el número hardcoded.

---

## INSTRUCCIONES OPERATIVAS PARA EL AGENTE CORRECTOR

1. Procesar los ítems en orden de categoría: A → B → C → D → E → F → G → H.
2. Para cada corrección aplicada al `.tex`, registrar una entrada en `Changelog.md` con el formato definido en AGENTS.MD §2.1.
3. Para cada corrección que tenga relevancia directa con los comentarios de los revisores, actualizar también `RESPONSE_TO_REVIEWERS.md` con el formato definido en AGENTS.MD §2.2.
4. Los ítems de Categoría I deben añadirse como checkboxes en la sección `## ⚠️ [REQUIRES AUTHOR INPUT]` de `Changelog.md`.
5. NO inventar datos, números, métricas o justificaciones. Si una corrección requiere información que no está disponible, registrarla en `[REQUIRES AUTHOR INPUT]`.
6. Antes de finalizar, comparar el archivo editado con `ORIGINAL_PROHIBIDO_MODIFICAR_elsarticle-template-num-names.tex` para verificar que no se hayan eliminado ecuaciones, tablas o datos experimentales (AGENTS.MD §4).

---

*Revisión generada el 2026-06-11 por Claude Sonnet 4.6 con rol de Revisor Senior Q1.*
*Total de observaciones: 35 ítems clasificados en 9 categorías.*
