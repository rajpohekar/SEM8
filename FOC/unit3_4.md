# Fiber Optic Communication — Units 3 & 4
## Complete Exam-Oriented Answer Guide (SPPU Sem 8 E&TC)

> **How to use this file:** Every answer follows the university topper format — definition → diagram reference → explanation → equations → memory tricks → revision notes. Marks are mentioned alongside each question.

---

# UNIT 3 — PHOTODETECTORS

---

## Q 3.1 — What is a photodetector? Explain the photodetection process. *(Dec 23, 6 Marks)*

### Definition / Introduction

A **photodetector** (optical detector) is an optoelectronic device that absorbs optical energy and converts it into electrical energy. It forms the receiving end of any fiber optic communication link. The process of converting light to electricity is called **photodetection**.

### Diagram

**[Refer Diagram from PDF — Fig showing photodetector block]**

### Detailed Explanation — Three Steps of Photodetection

The photodetection process involves **three sequential steps:**

#### Step 1 — Absorption
- Optical energy (photons) falling on the photodetector is absorbed by it.
- Absorption of photons causes generation of **charged carriers** (electron-hole pairs).
- The photon energy must be ≥ bandgap energy of the material for absorption to occur.

#### Step 2 — Transportation of Carriers
- Newly generated carriers are transported across the **absorption region**.
- In some photodetectors (like APD), a **gain** is applied to these carriers during transport.
- Transport is driven by the applied electric field (reverse bias).

#### Step 3 — Generation of Photocurrent
- After transportation, the carriers are collected and current flows in the **external circuit**.
- This current, caused by incident photons, is called **photocurrent (I_ph)**.

### Important Exam Keywords
- Optoelectronic device
- Absorption region
- Photocurrent
- Electron-hole pair
- Inner photoelectric effect

### Memory Trick
**"ATG"** — **A**bsorption → **T**ransportation → **G**eneration

### Common Mistakes
- Saying photodetector "emits" light — it **absorbs** light.
- Confusing photocurrent with dark current — dark current flows even without light.
- Forgetting that transportation is driven by reverse bias electric field.

### 2-Minute Revision Notes
- Photodetector: converts optical → electrical
- 3 steps: Absorption → Transportation → Photocurrent
- Reverse bias applied to widen depletion region for better absorption

### 30-Second Revision
- Photodetector absorbs photons
- Generates electron-hole pairs
- Carriers transported by electric field
- Photocurrent flows in external circuit
- Process = Inner Photoelectric Effect

### 10-Second Revision
**ATG** = Absorption → Transport → Generate photocurrent

### Expected University Questions
- What is a photodetector? Explain its working.
- Describe the photodetection process with steps.
- What are the requirements of photodetector materials?

### Final University Answer Summary
A photodetector is an optoelectronic device that converts optical signals into electrical signals. The photodetection process involves three steps: absorption of photons to generate electron-hole pairs, transportation of carriers across the depletion region under applied electric field, and collection of carriers to produce photocurrent in the external circuit. Materials like Si, Ge, and InGaAs are commonly used depending on the operating wavelength. The process is also known as the Inner Photoelectric Effect.

---

## Q 3.2 — Requirements of Material Selection for Photodetectors *(May 23, Dec 24, 5 Marks)*

### Definition / Introduction
The material chosen for a photodetector must enable efficient photon absorption and carrier generation. The material must support transitions of charged carriers between valence and conduction bands when exposed to incoming photons.

### Detailed Explanation

#### Common Photodetector Materials

| Material | Wavelength Range | Dark Current | Responsivity | Noise |
|----------|-----------------|--------------|--------------|-------|
| Silicon (Si) | Up to ~1.1 μm | Low | Low | Less (large bandgap) |
| Germanium (Ge) | Up to ~1.6 μm | High | High | More |
| InGaAs (I-V alloy) | 1.0–1.6 μm | Low | Good | Low |
| Lead Sulfite (PbS) | IR range | — | — | — |

#### Key Material Requirements
1. **Bandgap Energy (E_g):** Must match the operating wavelength — photon energy ≥ E_g
2. **Dark Current:** Should be as low as possible to reduce noise
3. **Responsivity:** Should be high — more electrical output per unit optical input
4. **Carrier Mobility:** High mobility allows faster response
5. **Temperature Stability:** Performance should not degrade with temperature changes
6. **Compatibility:** Should be compatible with fiber optic wavelength windows (850 nm, 1310 nm, 1550 nm)

### Memory Trick
**"BIRDS"** — **B**andgap, **I**mproved responsivity, **R**educed dark current, **D**rift velocity (high), **S**tability

### Common Mistakes
- Choosing Si for 1550 nm applications — Si cutoff is ~1.1 μm
- Ignoring dark current in material comparison
- Not relating bandgap energy to operating wavelength

### 2-Minute Revision Notes
- Si: low noise, low dark current, limited to 850 nm window
- Ge: wide range, high dark current, more noise
- InGaAs: best for 1310/1550 nm windows, low dark current

### 10-Second Revision
**Si (low noise) → Ge (wide range, noisy) → InGaAs (best for 1550 nm)**

---

## Q 3.3 — Performance and Compatibility Requirements of Photodetectors *(Dec 23, May 24, 6 Marks)*

### Detailed Explanation — Requirements Point-wise

1. **High sensitivity at operating wavelengths**
   - Second-generation systems operate above 1.1 μm (lower attenuation + dispersion)
   - Detector must be sensitive in these windows

2. **High fidelity**
   - Must reproduce received signal waveform accurately
   - For analog transmission: response must be **linear** over wide range

3. **Large electrical response**
   - Should produce maximum electrical signal for given optical power
   - Implies **high quantum efficiency (η)**

4. **Short response time / Large bandwidth**
   - Single-channel SM fiber systems reach tens of GHz
   - Fast response is essential for high bit-rate systems

5. **Minimum noise**
   - Dark current, leakage currents, shunt conductance must be low
   - Low noise floor allows detection of weak signals

6. **Stability**
   - Performance must be independent of ambient conditions
   - Temperature, humidity changes should not affect output

7. **Small physical size**
   - Compact detector required for efficient coupling to the fiber

8. **High reliability**
   - Must operate continuously at room temperature for many years

9. **Low cost**
   - Economically viable for large-scale deployment

### Memory Trick
**"SHLSMSR-C"** — **S**ensitivity, **H**igh fidelity, **L**arge response, **S**hort time, **M**inimum noise, **S**tability, **R**eliability, **C**ost

### Common Mistakes
- Not mentioning operating wavelength sensitivity
- Forgetting noise as a requirement
- Missing physical size requirement

### 10-Second Revision
**9 requirements: Sensitivity, Fidelity, Response, Bandwidth, Noise, Stability, Size, Reliability, Cost**

---

## Q 3.4 — Define Quantum Efficiency and Responsivity *(Dec 23, 6 Marks)*

### Definition / Introduction

**Responsivity (R)** and **Quantum Efficiency (η)** are the two most fundamental parameters of any photodetector that quantify how efficiently it converts optical power into electrical current.

### Mathematical Equations

#### (i) Responsivity (R)
Responsivity is the ratio of photocurrent generated to the incident optical power:

$$R = \frac{I_{ph}}{P_{inc}} \quad \text{(A/W)}$$

Also expressed as:

$$R = \frac{\eta \lambda (\mu m)}{1.24} \quad \text{(A/W)}$$

$$R = \frac{\eta q}{hf} = \frac{\eta q \lambda}{hc}$$

Where:
- I_ph = photocurrent (A)
- P_inc = incident optical power (W)
- η = quantum efficiency
- λ = wavelength (μm)
- q = electron charge = 1.602 × 10⁻¹⁹ C
- h = Planck's constant = 6.626 × 10⁻³⁴ J·s
- c = speed of light = 3 × 10⁸ m/s
- f = frequency of light (Hz)

#### (ii) Quantum Efficiency (η)
Ratio of generated charge carriers to incident photons:

$$\eta = \frac{\text{Number of generated charge carriers}}{\text{Number of incident photons}}$$

$$\eta_{ext} = \frac{I_{ph}/q}{P_{inc}/hf} = \frac{I_{ph} \cdot hf}{q \cdot P_{inc}}$$

**Internal quantum efficiency (η_i):**

$$\eta_i = \frac{\text{Number of pairs generated}}{\text{Number of photons absorbed}}$$

- η_ext ≤ 1 (external, includes reflection losses)
- η_i is typically higher (internal only)

### Important Exam Keywords
- Spectral responsivity
- Quantum efficiency
- Photocurrent
- Incident optical power
- Internal vs external quantum efficiency

### Memory Trick
**"R = ηλ/1.24"** — Responsivity equals eta-lambda over 1.24

### Common Mistakes
- Mixing up η_ext and η_i definitions
- Forgetting units of R = A/W
- Not substituting correct λ in micrometres in the formula R = ηλ/1.24

### 2-Minute Revision Notes
- R = I_ph / P_inc (A/W)
- R = ηλ/1.24 (λ in μm)
- η = carriers generated / photons incident
- η_ext uses photons incident; η_i uses photons absorbed

### 10-Second Revision
**R = ηλ/1.24 → η = I_ph·hf / (q·P_inc)**

---

## Q 3.5 — Long Cut-off Wavelength (λ_c) *(May 24, 8 Marks)*

### Definition
The **long cut-off wavelength (λ_c)** is the maximum wavelength at which a photodetector can operate — i.e., the wavelength at which detector sensitivity drops to 50% of its maximum value. Wavelengths greater than λ_c are **not detected**.

### Mathematical Equation

$$\lambda_c = \frac{hc}{E_g} = \frac{1240}{E_g (eV)} \text{ nm}$$

### Calculation for Silicon (Si)
- E_g of Si = 1.12 eV

$$\lambda_c = \frac{1240}{1.12} = 1107.14 \text{ nm} \approx 1.1 \mu m$$

### Factors Affecting λ_c
1. Bandgap energy (E_g) — inversely proportional
2. Material properties
3. Detector design / doping

### Memory Trick
**"λ_c = 1240 / E_g"** — Easy formula. 1240 is the product of h and c in eV·nm units.

### Common Mistakes
- Using E_g in Joules instead of eV in the formula
- Forgetting the wavelength unit (nm)
- Confusing λ_c with peak sensitivity wavelength

### 10-Second Revision
**λ_c = 1240 / E_g(eV) → Si: λ_c ≈ 1107 nm**

---

## Q 3.6 — Working of P-N Photodiode *(Dec 23, 6 Marks)*

### Definition / Introduction
A **P-N photodiode** is the simplest semiconductor photodetector consisting of a P-N junction operated under **reverse bias**. Incident light generates electron-hole pairs in the depletion region, producing photocurrent.

### Diagram
**[Refer Diagram from PDF — Fig 1: P-N junction photodiode, Fig 2: Cross-section, Fig 3: Working, Fig 4: V-I characteristics]**

### Construction
- P-N junction with applied **reverse bias**
- Depletion region forms between P and N layers
- Depletion region width increases with reverse bias
- Upper P layer is made **thin** so maximum light reaches depletion region

### Working
1. Incident light illuminates the P-N junction → covalent bonds are ionized
2. Photons with energy > 1.1 eV generate **electron-hole pairs** in depletion region
3. Built-in electric field separates carriers: electrons toward N, holes toward P
4. Carriers are collected at respective terminals → **photocurrent flows**
5. Pairs generated outside depletion region may diffuse in but mostly **recombine**

### V-I Characteristics
- Operated in **reverse bias region** only
- Dark condition: very small **dark current** flows
- With light: photocurrent increases proportionally with light intensity
- More light intensity → more photocurrent

### Key Trade-off
- Wider depletion region → more photon absorption → **better sensitivity**
- But wider depletion region → longer transit time → **slower response**
- → Always a compromise between sensitivity and speed

### Two Types of Excitation
- **Intrinsic Excitation:** Electron excited from valence to conduction band by photon
- **Extrinsic Excitation:** Excitation through impurity energy levels

### Important Exam Keywords
- Reverse bias, Depletion region, Electron-hole pair, Photocurrent, Dark current, Transit time, Inner photoelectric effect

### Memory Trick
**"ICES"** — **I**lluminate → **C**reate EHP → **E**lectric field separates → **S**ignal (photocurrent)

### Common Mistakes
- Saying P-N photodiode is forward biased — it's always **reverse biased**
- Ignoring the trade-off between depletion width and transit time
- Forgetting that pairs formed outside depletion region mostly recombine

### 2-Minute Revision Notes
- Reverse biased P-N junction
- Light → EHP in depletion region
- Electric field separates carriers
- Photocurrent ∝ incident light intensity
- Trade-off: wider depletion = more absorption but slower response

### 10-Second Revision
**Light → EHP → separated by E-field → photocurrent (reverse biased)**

---

## Q 3.7 — Numerical: Quantum Efficiency and Responsivity *(Dec 23, 6 Marks)*

### Given
- Incident photons = 3 × 10¹¹
- Wavelength λ = 0.85 μm
- Collected electrons = 1.2 × 10¹¹

### Formula

$$\eta = \frac{\text{Electrons collected}}{\text{Incident photons}}$$

$$R = \frac{\eta q \lambda}{hc}$$

### Substitution & Calculation

**Quantum Efficiency:**
$$\eta = \frac{1.2 \times 10^{11}}{3 \times 10^{11}} = 0.4 = 40\%$$

**Responsivity:**
$$R = \frac{0.4 \times 1.602 \times 10^{-19} \times 0.85 \times 10^{-6}}{6.626 \times 10^{-34} \times 3 \times 10^{8}}$$

$$\boxed{R = 0.274 \text{ A/W}}$$

### Shortcut Method
$$R = \frac{\eta \lambda}{1.24} = \frac{0.4 \times 0.85}{1.24} = \frac{0.34}{1.24} = 0.274 \text{ A/W}$$

### Common Exam Mistakes
- Using λ in metres instead of μm in shortcut formula
- Forgetting to convert η to decimal (40% → 0.4)
- Wrong unit for R (must be A/W)

### Memory Formula
**R = ηλ/1.24** (λ in μm, R in A/W)

---

## Q 3.8 — Numerical: Operating Wavelength and Optical Power *(May 23, 6 Marks)*

### Given
- η = 65% = 0.65
- Photon energy E = 1.5 × 10⁻¹⁹ J
- Photocurrent I_p = 2.5 μA = 2.5 × 10⁻⁶ A

### Part (i) — Operating Wavelength

$$\lambda = \frac{hc}{E} = \frac{6.626 \times 10^{-34} \times 3 \times 10^8}{1.5 \times 10^{-19}}$$

$$\boxed{\lambda = 1.325 \text{ μm}}$$

### Part (ii) — Required Optical Power

$$R = \frac{\eta q}{E} = \frac{0.65 \times 1.602 \times 10^{-19}}{1.5 \times 10^{-19}} = 0.694 \text{ A/W}$$

$$P_{opt} = \frac{I_P}{R} = \frac{2.5 \times 10^{-6}}{0.694}$$

$$\boxed{P_{opt} = 3.6 \text{ μW}}$$

### Common Exam Mistakes
- Using λ in m instead of μm in the 1.24 shortcut
- Incorrect R calculation when E is given in Joules

---

## Q 3.9 — Numerical: Responsivity, Optical Power, Number of Photons *(Dec 23, 6 Marks)*

### Given
- η = 50% = 0.5, λ = 0.9 μm, I_P = 10⁻⁶ A

### Part (i) — Responsivity
$$R = \frac{\eta \lambda}{1.24} = \frac{0.5 \times 0.9}{1.24} = \boxed{0.3629 \text{ A/W}}$$

### Part (ii) — Received Optical Power
$$P_{opt} = \frac{I_P}{R} = \frac{10^{-6}}{0.3626} = \boxed{2.758 \text{ μW}}$$

### Part (iii) — Number of Received Photons
$$E = \frac{hc}{\lambda} = \frac{6.626 \times 10^{-34} \times 3 \times 10^8}{0.9 \times 10^{-6}} = 2.2087 \times 10^{-19} \text{ J}$$

$$N = \frac{I_P}{R \cdot E} = \frac{10^{-6}}{0.3626 \times 2.2087 \times 10^{-19}} = \boxed{1.249 \times 10^{13}}$$

### Common Exam Mistakes
- Wrong unit for E (must be in Joules)
- Forgetting to compute E_photon before finding N

---

## Q 3.10 — P-I-N Photodiode: Structure and Operation *(Dec 24, 6 Marks)*

### Definition / Introduction
A **P-I-N photodiode** has an undoped intrinsic (i) layer inserted between the P⁺ and N⁺ regions. This larger depletion region improves sensitivity, bandwidth, and reduces capacitance compared to a simple P-N photodiode.

### Diagram
**[Refer Diagram from PDF — Fig 1: Construction of PIN diode, Fig 2: PIN photodiode structure, Fig 2: Spectral response curve]**

### Construction
- Structure: P⁺ | i (intrinsic) | N⁺
- Resistivity of i-layer: 10 Ω/cm to 100 kΩ/cm
- Resistivity of P⁺, N⁺ layers: < 1 Ω
- i-layer has much larger depletion area
- Material: Silicon (Si) or InGaAs

### Working

#### Forward Biased PIN Diode
- Charges injected from P and N into i-region
- i-region resistance decreases → acts as variable resistor
- Carriers not immediately recombined — stored in i-region

#### Reverse Biased PIN Diode
- Width of depletion region increases
- i-region completely depleted at **swept voltage**
- Diode behaves like a **capacitor** (P = +ve plate, N = −ve plate, i = insulator)

### Spectral Response
**[Refer Diagram from PDF — Fig 2: Spectral response of PIN photodiode]**

- **UV region (short λ):** EHP generated in P-layer → recombine before reaching depletion region → low response
- **Visible region:** EHP generated in depletion region → photocurrent developed → peak response
- **IR region (long λ):** Photon energy too low → no EHP in depletion region → response drops

### Important Exam Keywords
- Intrinsic layer, Swept voltage, Variable resistance, Depletion capacitance, Spectral response

### Memory Trick
**"PIN = P-Intrinsic-N → Better than PN"**

### Common Mistakes
- Confusing i-layer resistivity with P⁺/N⁺ resistivity
- Saying PIN only works in forward bias — it's used in **reverse bias** for photodetection
- Forgetting the spectral response curve explanation

### 2-Minute Revision Notes
- PIN: P⁺ | i | N⁺ structure
- i-layer: wide depletion, low capacitance, fast response
- Reverse bias: acts as capacitor
- Spectral response: peak in visible, drops at UV and IR ends

### 10-Second Revision
**PIN = wider depletion → lower capacitance → higher bandwidth → better detector**

---

## Q 3.11 — Compare P-N vs P-I-N Photodetectors *(May 24, 6 Marks)*

### Comparison Table

| Sr. No. | Parameter | P-N Photodiode | P-I-N Photodiode |
|---------|-----------|---------------|-----------------|
| 1 | Structure | 2 layers: P-type & N-type | 3 layers: P-type, Intrinsic, N-type |
| 2 | Depletion Width | Narrow | Wide |
| 3 | Response Time | Slow | Fast |
| 4 | Capacitance | Higher | Lower |
| 5 | Bandwidth | Lower | Higher |
| 6 | Dark Current | Higher | Lower |
| 7 | Sensitivity | Lower | Higher |
| 8 | Precision | Low precision detection | High precision detection |
| 9 | Bias Voltage | Low reverse bias | Low reverse bias |
| 10 | Cost | Cheaper | Slightly costlier |

### Design Perspective — Usefulness
- **P-N:** Cheaper, suitable for low-speed, low-cost applications
- **P-I-N:** Preferred for high-speed, high-sensitivity applications because:
  - Less noise, Good frequency response, Accepts high reverse voltages
  - Less dark current, Linear, Large depletion region
  - Low junction capacitance, High response speed

### Memory Trick
**"PIN is BETTER" — B**andwidth, **E**fficiency, **T**ransit time (lower), **T**emperature stable, **E**xact, **R**esponsive

### 10-Second Revision
**PIN > PN in every performance metric — only PN wins on cost**

---

## Q 3.12 — Noise Currents in PIN Photodiode *(6 Marks)*

### Four Types of Noise in PIN Photodiode

#### (a) Photon Noise
- Random fluctuations in the **arrival rate** of photons
- Causes random fluctuations in input → output signal
- Also called **quantum noise**

#### (b) Shot Noise
- Caused by **dark current** and **background radiation**
- Thermal generation of EHP in depletion region

$$I_{shot} = \sqrt{2qB(I_D + I_P)}$$

Where:
- q = 1.602 × 10⁻¹⁹ C, B = Bandwidth (Hz)
- I_D = dark current, I_P = photocurrent

#### (c) Johnson Noise (Thermal Noise)
- Random motion of charge carriers at thermal equilibrium

$$I_{thermal} = \sqrt{\frac{4KTB}{R_T}}$$

Where:
- K = 1.38 × 10⁻²³ J/K (Boltzmann's constant)
- T = temperature (K), B = bandwidth, R_T = total resistance

#### (d) Generation-Recombination Noise
- Fluctuations in recombination rates of carriers
- Generally very small; often negligible

### Total Noise Current

$$I_{total} = \sqrt{I_{thermal}^2 + I_{shot}^2}$$

### Signal-to-Noise Ratio (SNR)

$$\frac{S}{N} = \frac{I_P^2}{I_{thermal}^2 + I_{total}^2 \cdot F_n}$$

Where F_n = amplifier noise figure

### Memory Trick
**"PSJG"** — **P**hoton, **S**hot, **J**ohnson (thermal), **G**eneration-recombination

### Common Mistakes
- Forgetting F_n (noise figure) in SNR formula
- Using wrong temperature (must be in Kelvin, not Celsius)

### 10-Second Revision
**4 noises: Photon, Shot (dark current), Johnson (thermal), GR (small). Total = √(thermal² + shot²)**

---

## Q 3.13 — Avalanche Photodiode (APD): Structure, Working, Advantages *(May 24, Dec 23, Dec 24, 6 Marks)*

### Definition / Introduction
An **Avalanche Photodiode (APD)** operates with reverse bias close to breakdown voltage. It exploits the **impact ionization** process to achieve internal current multiplication, providing gain without an external amplifier.

### Diagram
**[Refer Diagram from PDF — Fig 1: Constructional Details of APD, Fig 2: Construction of RAPD]**

### Construction (RAPD — Reach-Through APD)
- Configuration: P⁺ – π – P – N⁺ (or P⁺ – P – N⁺)
- Two heavily doped regions: P⁺ (anode), N⁺ (cathode)
- Two lightly doped regions: π and P
- P⁺ layer = thin, for photon entry
- P–N⁺ region = high resistivity region where **impact ionization** occurs
- Depletion layer width is thinner than in PIN

### Working
1. Reverse bias near breakdown applied
2. Light incidents on P⁺ layer → EHP generated in π layer
3. Carriers move with **saturation velocity** under high electric field
4. Electrons enter high-resistivity P–N⁺ region
5. **Impact Ionization:** Fast electrons collide with lattice → new EHP generated
6. New carriers generate more carriers → **avalanche multiplication**
7. Electric field for impact ionization: 10⁴ to 10⁵ V/cm
8. **Gain (M):** up to 200 obtainable

$$M = \frac{\text{Multiplied photocurrent}}{I_P}$$

### Advantages
1. High sensitivity range
2. Detects low-intensity light
3. Single photon generates many carrier pairs
4. Quick response time
5. No external amplifier needed

### Disadvantages
1. Requires high operating voltage
2. Output is non-linear
3. High range of noise (avalanche noise)
4. Low reliability
5. Uses high reverse bias

### Applications
- Long-distance fiber optic links
- High bit-rate systems
- Optical power meters

### Important Exam Keywords
- Impact ionization, Multiplication factor M, Saturation velocity, Avalanche noise, Breakdown voltage

### Memory Trick
**"ABCM"** — **A**pply high bias → **B**ias near breakdown → **C**ollision (impact ionization) → **M**ultiplication

### Common Mistakes
- Saying APD has forward bias — it requires **high reverse bias**
- Forgetting that multiplication gain M can be up to 200
- Confusing impact ionization with stimulated emission

### 2-Minute Revision Notes
- APD = PIN + internal gain
- Impact ionization → avalanche multiplication
- E-field needed: 10⁴–10⁵ V/cm
- Gain M up to 200
- Disadvantage: high voltage, non-linear output

### 10-Second Revision
**APD = PIN + Avalanche Gain (M≤200) via Impact Ionization at near-breakdown bias**

---

## Q 3.14 — Noise Mechanisms in APD *(6 Marks)*

### Three Types of Noise in APD

#### (i) Shot Noise
- From primary currents: photocurrent, dark current, background current
- Small because these are primary (un-multiplied) currents

$$i_{shot} = \sqrt{2q(I_{ph} + I_B + I_D) \cdot G^2 \cdot F \cdot B}$$

Where G = gain, F = excess noise factor, B = bandwidth

#### (ii) Thermal Noise
- From resistance variations in APD

$$i_{thermal} = \sqrt{\frac{4KTB}{R_{eq}}}$$

#### (iii) Avalanche Noise (Main Noise Source)
- Generated because rate of secondary carrier generation is not constant
- Variations in secondary carrier generation → noise current
- **Reduction method:** Make avalanche process asymmetric — only one carrier type (electrons OR holes) generates secondary carriers

$$\text{To minimize: } \frac{\alpha_e}{\alpha_h} \gg 1 \quad \text{(or } \ll 1\text{)}$$

Where α_e = electron ionization coefficient, α_h = hole ionization coefficient

### Memory Trick
**"STA"** — **S**hot (primary), **T**hermal (resistance), **A**valanche (main source)

### Common Mistakes
- Saying shot noise is the main noise in APD — **avalanche noise** is the dominant one
- Forgetting excess noise factor F in shot noise formula

### 10-Second Revision
**APD main noise = Avalanche noise. Reduce by asymmetric ionization (α_e >> α_h)**

---

## Q 3.15 — Compare PIN Photodiode vs APD *(May 23, 6 Marks)*

### Comparison Table

| Sr. No. | Parameter | PIN Photodiode | APD |
|---------|-----------|---------------|-----|
| 1 | Structure | P⁺–i–N⁺ (undoped i-layer) | P⁺–π–P–N⁺ (π layer) |
| 2 | Gain | No internal gain | Internal gain (M up to 200) |
| 3 | External Amplifier | Required | Not required |
| 4 | Response Time | Fast | Comparatively slower |
| 5 | Output Current | Small | Large (amplified) |
| 6 | Noise Types | Photon, Shot, Johnson, GR | Shot, Thermal, Avalanche |
| 7 | Shot Current | I_shot = √(2qI_D·B) | I_shot = √(2q(I_ph+I_B+I_D)G²FB) |
| 8 | Sensitivity | Lower | Higher sensitivity |
| 9 | Reverse Bias | Low (5–15 V) | High (100–300 V) |
| 10 | Temperature Stability | Good | Poor |

### Memory Trick
**"APD = PIN + Power but at a Price"** (higher voltage, noise, complexity)

### 10-Second Revision
**PIN: simple, cheap, low noise. APD: high gain, high voltage, high noise, long-distance use.**

---

## Q 3.16 — Numerical: SNR Calculation for PIN Photodiode *(May 23, 6 Marks)*

### Given
- λ = 870 nm, B = 20 MHz, η = 65%, I_D = 1 nA
- C = 8 pF, Noise figure = 3 dB, P_opt = 5 μW, R_Load = 1 kΩ

### Step-by-Step Solution

**Responsivity:**
$$R = \frac{\eta\lambda}{1.24} = \frac{0.65 \times 0.87}{1.24} = 0.4557 \text{ A/W}$$

**Photocurrent:**
$$I_P = P_0 \times R = 5 \times 10^{-6} \times 0.4557 = 2.278 \text{ μA}$$

**Shot Noise:**
$$I_{shot} = \sqrt{2qB(I_P + I_D)} = \sqrt{2 \times 1.602 \times 10^{-19} \times 20 \times 10^6 \times 2.279 \times 10^{-6}}$$
$$\boxed{I_{shot} = 3.822 \text{ nA}}$$

**Thermal Noise (R_Load = 1 kΩ):**
$$I_{thermal} = \sqrt{\frac{4KTB}{R_L}} = \sqrt{\frac{4 \times 1.38 \times 10^{-23} \times 298 \times 20 \times 10^6}{10^3}}$$
$$\boxed{I_{thermal} = 18.138 \text{ nA}}$$

**Total Noise:**
$$I_{total} = \sqrt{I_{thermal}^2 + I_{shot}^2} = 18.536 \text{ nA}$$

**Noise Figure:** 3 dB → F_n = 10^(3/10) = 2

**SNR:**
$$\frac{S}{N} = \frac{I_P^2}{I_{thermal}^2 + I_{total}^2 \cdot F_n} = \frac{(2.278 \times 10^{-6})^2}{(3.435 \times 10^{-16}) + (3.435 \times 10^{-16} \times 2)}$$
$$\boxed{\frac{S}{N} = 37.019 \text{ dB}}$$

### Common Exam Mistakes
- Using T in Celsius instead of Kelvin
- Not converting noise figure from dB to linear (F_n = 2 for 3 dB)
- Forgetting to include I_D in shot noise formula

---

## Q 3.17 — Numerical: Avalanche Gain of APD *(Dec 24, 8 Marks)*

### Given
- η = 65%, λ = 900 nm = 900 × 10⁻⁹ m
- P_opt = 0.5 μW, Multiplied photocurrent = 10 μA

### Solution

**Responsivity:**
$$R = \frac{\eta\lambda}{1.24} = \frac{0.65 \times 0.9}{1.24} = 0.4714 \text{ A/W}$$

**Primary Photocurrent:**
$$I_P = P_0 \times R = 0.5 \times 10^{-6} \times 0.4714 = 235.73 \text{ nA}$$

**Avalanche Gain (Multiplication Factor):**
$$M = \frac{\text{Multiplied current}}{I_P} = \frac{10 \times 10^{-6}}{235.73 \times 10^{-9}}$$
$$\boxed{M = 42.42}$$

### Memory Formula
$$M = \frac{I_{multiplied}}{I_P} = \frac{I_{multiplied}}{P_0 \times R}$$

---

## Q 3.18 — Phototransistor: Construction and Working *(May 24, 6 Marks)*

### Definition
A **phototransistor** is a light-sensitive transistor where incident light replaces the base current. It provides both detection and amplification of optical signals.

### Diagram
**[Refer Diagram from PDF — Fig 1: Construction of Phototransistor, Fig 1: Phototransistor in circuits]**

### Construction
- Similar to BJT but with **larger base-collector junction area** for more light absorption
- Two or three terminal device (base terminal may be omitted)
- Materials: Si or Ge (homogeneous)
- Collector-base region formed by ion implantation and diffusion

### Working
- Light enters through the base region
- Output taken from **emitter terminal**
- Magnitude of photocurrent depends on **light intensity**
- Can operate in 3 regions: cut-off (switch OFF), active (amplification), saturation (switch ON)

### Factors Affecting Photocurrent
1. DC current gain (β) of transistor
2. Response time / time constant
3. Luminous sensitivity = I_photoelectric / incident luminous flux
4. Area of collector-base junction (larger = more photocurrent)
5. Wavelength of incident light (higher λ → lower frequency → less energy)

### Advantages
- Detection + amplification in one device
- No external amplifier needed for low-level signals

### Disadvantages
- Slower response than PIN/APD
- More noise

### Memory Trick
**"DTAL WA"** — **D**C gain, **T**ime constant, **A**rea (CB), **L**uminous sensitivity, **W**avelength, **A**mplification

### 10-Second Revision
**Phototransistor = photodetector + amplifier. Light enters base, output from emitter.**

---

## Q 3.19 — Noise Types in Photodetector/Receiver *(Dec 24, 6 Marks)*

### Noise Classification
**[Refer Diagram from PDF — Fig 1: Noise classification tree, Fig 2: Noise sources block diagram]**

Noise = **Internal** (thermal, dark current, quantum) + **External** (atmospheric, equipment-generated)

### (a) Thermal Noise (Johnson Noise)
- Spontaneous voltage/current fluctuations due to thermal interaction in resistors

$$I_{thermal} = \sqrt{\frac{4KTB}{R}}$$

### (b) Dark Current Noise (Shot Noise)
- Small reverse current even with no incident light
- Produces shot noise

$$I_{shot} = \sqrt{2qBI_D}$$

### (c) Quantum Noise
- Random arrival of photons at detector (Poisson distribution)
- Important for setting **quantum limit** of digital transmission
- Probability of detecting M photons in time τ:

$$P(M) = \frac{M_n^M \cdot e^{-M_n}}{M!}$$

- Rate of electron generation: $r_e = \frac{\eta_q P_{opt}}{hf}$
- Average photons detected: $M_n = r_e \cdot \tau$

### Memory Trick
**"TDQ"** — **T**hermal, **D**ark current, **Q**uantum (in order of common importance)

### Common Mistakes
- Confusing dark current noise with quantum noise
- Not using Kelvin for temperature in thermal noise formula
- Forgetting Poisson distribution for quantum noise

### 10-Second Revision
**Thermal (resistor), Dark current (shot, no-light current), Quantum (random photon arrivals)**

---

## Q 3.20 — Receiver Structure *(Dec 24, 5 Marks)*

### Block Diagram
**[Refer Diagram from PDF — Fig 1: Block schematic of receiver structure, Fig 2: Probability density function]**

### Blocks of Receiver
1. **Photo Detector** → converts optical to electrical
2. **Low Noise Pre-Amplifier** → amplifies weak signal
3. **AGC Control + Equalization** → gain control + compensates dispersion
4. **Error Detection Circuit** → compares with threshold
5. **Driver for Optical Source** → drives regenerated signal

### Key Concepts

#### Threshold Level
- Above threshold → Logic '1' decoded
- Below threshold → Logic '0' decoded
- Too much dispersion → wrong decisions

#### Gaussian PDF (for BER analysis)
$$P(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-(x-m)^2/2\sigma^2}$$

- m = mean value
- σ = standard deviation (rms noise)

#### Bit Error Rate (BER)
$$BER = \frac{N_e}{N_t} = \frac{N_e}{B_t}$$

- BER range for good performance: 10⁻⁹ to 10⁻¹²
- Receiver **sensitivity** = minimum optical power for required BER

### Important Exam Keywords
- BER, Threshold level, Gaussian PDF, Receiver sensitivity, Regenerative repeater

### Memory Trick
**"PLACED"** — **P**hotodetector → **L**ow-noise amp → **A**GC → **C**omparator → **E**rror detect → **D**river

### Common Mistakes
- Saying quantum noise is Gaussian — it's Poisson, but Gaussian approximation used for BER
- Confusing sensitivity with responsivity
- Forgetting threshold level concept

### 10-Second Revision
**BER = Errors/Total bits. Target: 10⁻⁹ to 10⁻¹². Sensitivity = min power for target BER.**

---
---

# UNIT 4 — FIBER OPTIC LINK DESIGN AND WDM SYSTEMS

---

## Q 4.1 — Simplex Point-to-Point Optical Link *(May 23, 6 Marks)*

### Definition / Introduction
A **point-to-point optical link** is the simplest fiber optic system connecting a single transmitter (light source + fiber) to a single receiver (detector). It is the basic building block of all fiber optic communication systems.

### Diagram
**[Refer Diagram from PDF — Fig 1: Point to point link showing Light Source → Optical Transmitter → Fiber → Optical Receiver]**

### System Requirements
The three key system requirements are:
1. **Transmission distance** — how far data must travel
2. **Channel bandwidth** — data rate capacity needed
3. **Bit Error Rate (BER)** — acceptable error rate (typically 10⁻⁹)

### Three Major Components

#### (i) Light Source Selection
| Parameter | LED | Laser Diode |
|-----------|-----|-------------|
| Cost | Low | High |
| Spectral width | 20–100 nm | 1–3 nm |
| Output pulse | Wide | Narrow (coherent) |
| Bit rate | Lower | Higher |
| Repeater spacing | Shorter | Longer |
| Launching power | Low | 10–15 dB more than LED |

**Selection factors:** Wavelength, Number of modes, Output power, Pulse area

#### (ii) Optical Fiber Selection
Selection depends on:
- Refractive index profile (step-index vs. graded-index)
- Losses (attenuation + dispersion)
- Acceptance angle / Numerical Aperture (NA)
- Core size
- Silica glass fiber → better accuracy than plastic

#### (iii) Detector Selection
| Detector | Advantages | Use case |
|----------|------------|----------|
| PIN | Low cost, temp-stable, low bias | Short/medium distance, lower bit rate |
| APD | High sensitivity, internal gain | Long distance, high bit rate |

**Selection factors:** Responsivity, Quantum efficiency, Noise, Noise Equivalent Power (NEP), Speed

### Other Components
- **Connectors** — demountable (connect/disconnect fibers)
- **Splices** — permanent fiber joints

### Important Exam Keywords
- BER, Spectral width, Repeater spacing, Responsivity, Launching power, Numerical Aperture

### Memory Trick
**"SFD"** — **S**ource → **F**iber → **D**etector (the three selection decisions)

### Common Mistakes
- Forgetting to mention BER as a system requirement
- Saying APD is always better — PIN is preferred for short distance (cost, stability)
- Not mentioning connectors and splices

### 2-Minute Revision Notes
- P2P link: Source → Fiber → Detector
- LED: cheap, wide spectrum; LD: expensive, narrow spectrum, +10–15 dB power
- PIN: cheap, stable; APD: high sensitivity, high voltage, long-distance
- System requirements: Distance, Bandwidth, BER

### 10-Second Revision
**P2P link = Source + Fiber + Detector. Choose by Distance, BW, BER.**

---

## Q 4.2 — Optical Power Loss Model / Link Power Budget *(May 24, 4 Marks)*

### Definition
The **optical power budget** allocates available optical power (from source to receiver) among loss-producing mechanisms to ensure adequate signal at the receiver.

### Diagram
**[Refer Diagram from PDF — Fig 1: Optical power loss model showing S → Connector → Fiber (α) → Splices → Connector → D]**

### Loss Equation
$$\text{Loss (dB)} = 10 \log\left(\frac{P_{out}}{P_{in}}\right)$$

### Power Budget Equation
$$P_T = P_S - P_R = 2l_c + \alpha L + l_{sp} \cdot N_{sp} + \text{System Margin}$$

Where:
- P_T = total allowed loss (dB)
- P_S = optical power of source (dBm)
- P_R = receiver sensitivity (dBm)
- l_c = connector loss (dB)
- α = fiber attenuation (dB/km)
- L = fiber length (km)
- l_sp = loss per splice (dB)
- N_sp = number of splices
- System margin = safety margin (typically 6 dB)

### Key Concepts
- **dBm** = 10 log(P in mW / 1 mW) — absolute power unit
  - 0 dBm = 1 mW, −10 dBm = 0.1 mW
- Losses in dB, powers in dBm
- Link is **viable** if allowed loss ≥ actual loss

### Memory Trick
**"PFAST"** — **P**ower(source) − **F**iber loss − **A**ttenuation − **S**plice/connector − **T**otal margin = Available

### Common Mistakes
- Mixing dB (loss) with dBm (power)
- Forgetting system margin in total loss
- Wrong number of splices (length/splice spacing, but boundary splices)

### 10-Second Revision
**Budget: P_allowed = P_source − P_receiver. Must be ≥ Total loss (fiber + splices + connectors + margin)**

---

## Q 4.3 — Numerical: Power Budget (10 km Link, RZ Code) *(6 Marks)*

### Given
- Length = 10 km, Rate = 20 Mbit/s, RZ code, λ = 0.85 μm
- LED power = 0.1 mW = −10 dBm
- Fiber attenuation = 2.5 dB/km
- Splices every 2 km, 0.3 dB/splice
- Connector loss at receiver = 1.5 dB
- Receiver sensitivity = −46 dBm, BER = 10⁻¹⁰
- Safety margin = 6 dB

### Solution

| Component | Loss (dB) | Running Margin (dB) |
|-----------|-----------|---------------------|
| LED output | −10 dBm | — |
| Receiver sensitivity | −46 dBm | — |
| **Allowed loss (P_T)** | −10−(−46) = **36 dB** | 36 |
| Fiber attenuation (2.5×10) | 25 dB | 36−25 = 11 |
| Splice loss (4×0.3) | 1.2 dB | 11−1.2 = 9.8 |
| Connector loss (receiver) | 1.5 dB | 9.8−1.5 = 8.3 |
| Safety margin | 6 dB | 8.3−6 = **2.3 dB** ✅ |

**Conclusion:** Allowed loss (36 dB) > Actual loss (33.7 dB). **Link is VIABLE** with 2.3 dB extra margin.

### Common Exam Mistakes
- Wrong splice count (10 km ÷ 2 km = 5 sections → **4 splices** in middle, not 5)
- Forgetting safety margin in total loss
- Converting mW to dBm incorrectly

---

## Q 4.4 — Numerical: Power Budget (80 km Single Mode Link) *(May 23, 3 Marks)*

### Given
- λ = 1550 nm, Rate = 622 Mb/s, L = 80 km
- Laser power = 13 dBm, Fiber loss = 0.35 dB/km
- Splice every 1 km, 0.1 dB/splice (79 splices in 80 km)
- Connector loss = 0.5 dB, APD sensitivity = −31 dBm
- Excess noise penalties = 1.5 dB

### Solution

| Component | Loss | Running Margin |
|-----------|------|----------------|
| Laser output | 13 dBm | — |
| APD sensitivity | −31 dBm | — |
| **Allowed loss** | 13−(−31) = **44 dB** | 44 |
| Splice loss (79×0.1) | 7.9 dB | 44−7.9 = 36.1 |
| Fiber loss (80×0.35) | 28 dB | 36.1−28 = 8.1 |
| Connector loss | 0.5 dB | 8.1−0.5 = 7.6 |
| Noise penalties | 1.5 dB | 7.6−1.5 = **6.1 dB** ✅ |

**Final system margin = 6.1 dB.** Link is viable.

---

## Q 4.5 — Numerical: Estimate Link Length *(Dec 23, 8 Marks)*

### Given
- LED power = 50 μW = −13 dBm
- Receiver sensitivity = −42 dBm
- Fiber flyhead losses = 1+1 = 2 dB (both ends)
- System margin = 6 dB
- Fiber attenuation = 3.5 dB/km

### Solution
$$P_T = -13 - (-42) = 29 \text{ dB (total allowed loss)}$$

$$29 = 2 + 6 + 3.5L$$

$$3.5L = 29 - 8 = 21$$

$$\boxed{L = 6 \text{ km}}$$

---

## Q 4.6 — Numerical: Power Budget & Maximum Fiber Distance *(May 24, 9 Marks)*

### Given
- P_source = −8 dBm, P_receiver = −38 dBm
- Length = 40 km, Attenuation = 0.40 dB/km
- 2 connector pairs × 0.75 dB, 5 splices × 0.1 dB
- System margin = 6 dB

### Solutions

#### (i) Total Connector and Splice Losses
- Total connector loss = 2 × 0.75 = **1.5 dB**
- Total splice loss = 5 × 0.1 = **0.5 dB**

#### (ii) Total Link Loss
$$= (0.40 \times 40) + 1.5 + 0.5 + 6 = 16 + 1.5 + 0.5 + 6 = \boxed{24 \text{ dB}}$$

#### (iii) Maximum Fiber Distance
$$P_T = -8 - (-38) = 30 \text{ dB}$$

$$30 = 1.5 + 0.5 + 6 + 0.40L$$

$$0.40L = 22 \Rightarrow \boxed{L_{max} = 55 \text{ km}}$$

### Common Exam Mistakes
- Forgetting system margin in total loss calculation
- Not separating connector and splice losses in part (i)

---

## Q 4.7 — Rise Time Budget *(May 24, Dec 23, 4–6 Marks)*

### Definition
**Rise time** of a linear system = time for response to increase from 10% to 90% of final output value when input changes abruptly.

The **rise time budget** determines the dispersion limitation of an optical link.

### Diagram
**[Refer Diagram from PDF — Fig 1: Rise Time concept, Fig 2: Rise Time Budget block diagram]**

### Total System Rise Time Equation

$$t_{sys} = \sqrt{t_{tx}^2 + t_{mod}^2 + t_{mat}^2 + t_{rx}^2}$$

### Four Components of Rise Time Budget

#### 1. Transmitter Rise Time (t_tx)
- Contributed by light source + driving circuitry
- Known from source specification

#### 2. Group Velocity Dispersion Rise Time (t_mat — Intramodal)
- Due to material dispersion and waveguide dispersion
- Each fiber section contributes its own dispersion
- Unit: ns/km → multiply by length L

#### 3. Modal Dispersion Rise Time (t_mod — Intermodal)
$$t_{mod} = \frac{440}{B_M}$$

$$B_M = \frac{B_0}{L^q}$$

Where:
- B_M = bandwidth of optical link (MHz)
- B_0 = bandwidth of 1 km cable
- q = 0.5 to 1 (empirical parameter)
- Unit: ns/km → multiply by length L

#### 4. Receiver Rise Time (t_rx)
- From photodetector response + 3-dB electrical bandwidth

$$t_{rx} = \frac{350}{B_{rx} \text{ (MHz)}} \text{ ns}$$

### Bandwidth-Rise Time Relations

| Format | Formula |
|--------|---------|
| **NRZ (Non-Return-to-Zero)** | $B_{T(max)} = \dfrac{0.70}{t_{sys}}$ |
| **RZ (Return-to-Zero)** | $B_{T(max)} = \dfrac{0.35}{t_{sys}}$ |

### Memory Trick
**"TMMR"** — **T**ransmitter, **M**aterial dispersion, **M**odal dispersion, **R**eceiver

### Common Mistakes
- Using RZ formula for NRZ (0.70 for NRZ, 0.35 for RZ)
- Not squaring each rise time before summing
- Forgetting to multiply ns/km by link length

### 10-Second Revision
**t_sys = √(t_tx² + t_mat² + t_mod² + t_rx²). NRZ: BW = 0.70/t_sys. RZ: BW = 0.35/t_sys**

---

## Q 4.8 — Numerical: Maximum Bit Rate (NRZ and RZ) *(Dec 24, 6 Marks)*

### Given
- L = 8 km, LED = 8 ns, Intermodal = 5 ns/km, Intramodal = 1 ns/km, Detector = 6 ns

### Solution

$$t_{sys} = \sqrt{(8)^2 + (5 \times 8)^2 + (1 \times 8)^2 + (6)^2}$$

$$= \sqrt{64 + 1600 + 64 + 36} = \sqrt{1764}$$

$$\boxed{t_{sys} = 42 \text{ ns}}$$

**Maximum Bit Rate (NRZ):**
$$B_{NRZ} = \frac{0.70}{42 \times 10^{-9}} = \boxed{16.6 \text{ Mbit/s}}$$

**Maximum Bit Rate (RZ):**
$$B_{RZ} = \frac{0.35}{42 \times 10^{-9}} = \boxed{8.3 \text{ Mbit/s}}$$

---

## Q 4.9 — Numerical: Rise Time Budget (Adequacy Check) *(6 Marks)*

### Given
- LED = 10 ns, Intermodal = 9 ns/km, Intramodal = 2 ns/km
- APD = 3 ns, L = 5 km, Required BW = 6 MHz

### Solution

$$t_{sys} = \sqrt{(10)^2 + (9 \times 5)^2 + (2 \times 5)^2 + (3)^2}$$

$$= \sqrt{100 + 2025 + 100 + 9} = \sqrt{2234} = \boxed{47.26 \text{ ns}}$$

$$B_{NRZ} = \frac{0.70}{47.26 \times 10^{-9}} = 14.81 \text{ Mbit/s}$$

Equivalent 3-dB optical bandwidth = 14.81/2 = **7.4 MHz**

**Required BW = 6 MHz < 7.4 MHz → System is ADEQUATE ✅**

---

## Q 4.10 — Numerical: Maximum NRZ Bit Rate (8 km Link) *(6 Marks)*

### Given
- LED = 10 ns, PIN = 6 ns, Intermodal = 10 ns/km, Intramodal = 5 ns/km, L = 8 km

### Solution

$$t_{sys} = \sqrt{(10)^2 + (10 \times 8)^2 + (5 \times 8)^2 + (6)^2}$$

$$= \sqrt{100 + 6400 + 1600 + 36} = \sqrt{8136} = 90.2 \text{ ns}$$

$$B_{NRZ} = \frac{0.70}{90.2 \times 10^{-9}} = \boxed{7.76 \text{ Mbit/s}}$$

---

## Q 4.11 — Numerical: Maximum Rise Time for RZ System *(May 23, 6 Marks)*

### Given
- L = 10 km, Intramodal = 0.2 ns/km, APD = 1 ns, Source = 4 ns
- RZ, Rate = 40 Mbps (intermodal = 0)

### Solution

**Actual rise time:**
$$t_{sys} = \sqrt{(4)^2 + (0.2 \times 10)^2 + (1)^2} = \sqrt{16 + 4 + 1} = \sqrt{21} = 4.58 \text{ ns}$$

**Maximum allowed rise time for RZ:**
$$t_{sys(max)} = \frac{0.35}{40 \times 10^6} = 8.75 \text{ ns}$$

**Actual (4.58 ns) < Maximum (8.75 ns) → Link operates SUCCESSFULLY ✅**

---

## Q 4.12 — WDM: Typical Implementation and Active Components *(6 Marks)*

### Definition
**Wavelength Division Multiplexing (WDM)** is a technique where multiple optical signals of different wavelengths are transmitted simultaneously through a single optical fiber, significantly increasing the capacity of the fiber link.

### Diagram
**[Refer Diagram from PDF — Fig 1: WDM block diagram, Fig 2: Bidirectional WDM]**

### WDM System Blocks
- **Multiple light sources:** Each emitting a unique wavelength (λ₁, λ₂, λ₃...)
- **Optical Multiplexer (MUX):** Combines all wavelengths into one fiber
- **Optical Fiber:** Carries all multiplexed wavelengths
- **Optical Demultiplexer (DEMUX):** Separates individual wavelengths
- **Detectors:** One for each wavelength

### Bidirectional WDM
- MUX/DEMUX1 acts as MUX for λ₁, λ₂ and DEMUX for λ₃, λ₄
- MUX/DEMUX2 acts as DEMUX for λ₁, λ₂ and MUX for λ₃, λ₄
- Enables **simultaneous bidirectional communication** over single fiber

### Active WDM Components
- Tunable lasers, Optical amplifiers (EDFA), Wavelength converters
- Optical switches, Modulators, SOA (Semiconductor Optical Amplifiers)

### Memory Trick
**"SMFMD"** — **S**ource → **M**UX → **F**iber → **M**UX/DEMUX → **D**etector

### 10-Second Revision
**WDM = Multiple λ on one fiber. MUX combines, DEMUX separates. Key: Bidirectional possible.**

---

## Q 4.13 — WDM Network Architecture and Components *(May 24, Dec 24, 6–8 Marks)*

### Diagram
**[Refer Diagram from PDF — Fig 1: General Architecture of wavelength routing mesh network]**

### WDM Network Elements

#### 1. Optical Line Terminals (OLTs)
- Used at **both ends** of a point-to-point link
- Contains: **Transponders** + Wavelength MUX/DEMUX
- **Transponder:** Interface device (also called adaptation device) between clients (IP router, SONET) and optical network
  - Client interface: SONET/SDH Short Reach (SR) interface
  - Converts client signal → optical network format (and vice versa)
- Wavelength multiplexer combines signals; amplifiers boost if needed
- **Optical Supervisory Channel (OSC):** Monitors amplifier performance; operates on separate wavelength

#### 2. Optical Add/Drop Multiplexers (OADMs)
- **Adds** new wavelengths to a fiber or **drops** (removes) specific wavelengths
- Architectures: Parallel, Modular parallel, Serial, Band drop
- Used in ring or mesh networks for traffic grooming

#### 3. Optical Cross Connects (OXCs)
- Used at nodes with large traffic or complex networks
- Works with OLTs, SONET/SDH, OADMs
- Functions:
  - Provides extra light paths automatically
  - Reconfigures existing light paths
  - Detects fiber cut/failure → provides alternate path
  - Switches optical signals between ports
  - Provides wavelength conversion
  - Contains internal multiplexing capabilities

### Memory Trick
**"OAX"** — **O**LT (terminals), **A**DM (add/drop), **X**-connect (cross)

### Common Mistakes
- Confusing OLT with transponder — transponder is a component inside OLT
- Forgetting OSC function
- Not mentioning failure recovery function of OXC

### 10-Second Revision
**OLT = terminal, OADM = add/drop, OXC = switching/routing. All form WDM mesh network.**

---

## Q 4.14 — Features of WDM Architecture *(6 Marks)*

### Diagram
**[Refer Diagram from PDF — Fig 1: Feature of WDM Architecture tree diagram]**

### Five Important Features

#### (i) Wavelength Reuse
- Multiple **light paths** can reuse the same wavelength as long as paths don't overlap
- Increases network capacity using limited number of wavelengths

#### (ii) Wavelength Conversion
- Required when light paths overlap (conflict)
- Also required at network boundaries to convert outside wavelengths to internal wavelengths
- Done by **wavelength converters** at nodes

#### (iii) Transparency
- Different light paths can carry data at **different rates and protocols**
- Protocol-insensitive (SONET-to-SONET or Router-to-Router on same network)
- WDM layer is transparent to client protocols

#### (iv) Circuit Switching
- Circuits (light paths) can be **set up and torn down** on demand
- Similar to circuit switching in telephone networks
- But **packet switching is not supported** at the optical layer

#### (v) Survivability
- Network can **detect failures** (fiber cut, element failure)
- Light paths are automatically **rerouted** through alternate paths

### Memory Trick
**"RWTCS"** — **R**euse, **W**avelength conversion, **T**ransparency, **C**ircuit switching, **S**urvivability

### 10-Second Revision
**5 WDM features: Reuse, Conversion, Transparency, Circuit switching, Survivability (fault tolerance)**

---

## Q 4.15 — Optical Isolator *(Dec 23, Dec 24, 6 Marks)*

### Definition
An **optical isolator** is a passive optical device that allows light propagation in the **forward direction only** and blocks backward-propagating (reflected) light.

### Diagram
**[Refer Diagram from PDF — Fig 1: Optical Isolator working with polarizers and Faraday rotator]**

### Key Parameters
| Parameter | Description | Typical Value |
|-----------|-------------|---------------|
| Insertion Loss | Loss in forward direction (minimize) | ~1 dB |
| Isolation | Loss in reverse direction (maximize) | 40–50 dB |

### Principle of Working — Faraday Effect
1. Incoming light has **vertical polarization (SOP)**
2. Passes through **Polarizer ①** (passes vertical SOP only)
3. **Faraday Rotor** rotates polarization by **45°**
4. **Polarizer ②** passes light at 45° orientation → forward light passes through
5. **Reflected light** (at 45°) passes through Polarizer ② → Faraday Rotor rotates by another 45° → now **horizontal SOP (90°)**
6. Polarizer ① blocks horizontal SOP → **Reflected light is blocked**

### Why Used?
- Laser source is affected when reflected light re-enters it
- Isolator prevents reflected light from disturbing laser oscillations
- Placed between laser source and fiber

### Important Exam Keywords
- Faraday Effect, State of Polarization (SOP), Insertion loss, Isolation, Non-reciprocal device

### Memory Trick
**"VFF-H Blocked"** — **V**ertical (forward) → **F**araday 45° → **F**orward passes. Reflected goes **H**orizontal → **Blocked**

### Common Mistakes
- Saying insertion loss should be maximized — it should be **minimized**
- Confusing isolator with circulator (isolator is 2-port; circulator is 3/4-port)
- Saying Faraday rotor rotates forward and backward differently — the key is it's **non-reciprocal**

### 2-Minute Revision Notes
- Isolator: one-way light travel
- Faraday rotor: 45° rotation
- Forward: Vertical → 45° → passes Polarizer ②
- Reflected: 45° → 90° (horizontal) → blocked by Polarizer ①
- Insertion loss: low (~1 dB). Isolation: high (40–50 dB)

### 10-Second Revision
**Isolator = Faraday rotation (45°). Forward passes, backward gets rotated 90° → blocked.**

---

## Q 4.16 — Optical Couplers *(6 Marks)*

### Definition
A **fiber optic coupler** is a device that distributes optical signal from one fiber among two or more fibers (splitting), or combines signals from multiple fibers into one (combining).

### Key Parameter — Coupling Ratio
$$\text{Coupling Ratio} = \frac{P_{out}}{P_{total\ input}} \times 100\%$$

Coupling ratio should be **minimum** (ideally 50:50 for 2×2 splitter).

### Types of 2×2 Optical Couplers

#### (i) Evanescent Wave Coupler
**[Refer Diagram from PDF — Fig 1: Evanescent wave coupler]**
- Two fiber cores are brought **parallel** for a certain **coupling length**
- Evanescent wave from fiber 1 penetrates into fiber 2
- Signal couples from one fiber to another
- Amount of coupling depends on coupling length and spacing

#### (ii) Fused Biconical Taper (FBT) Coupler — Twisted Pair
**[Refer Diagram from PDF — Fig 2: FBT coupler]**
- Two fibers are twisted together and **fused with heat**
- Core of one fiber acts as **cladding** for the other
- Coupling occurs in the fused (tapered) region
- Most common type — simple and low cost

### Formulas for Coupler Parameters

$$\text{Coupling Ratio} = \frac{P_2}{P_1 + P_2} \times 100\%$$

$$\text{Excess Loss} = 10 \log\left(\frac{P_0}{P_1 + P_2}\right)$$

$$\text{Insertion Loss (0→1)} = 10 \log\left(\frac{P_0}{P_1}\right)$$

$$\text{Return Loss (Crosstalk)} = 10 \log\left(\frac{P_3}{P_0}\right)$$

### Memory Trick
**"CEIR"** — **C**oupling ratio, **E**xcess loss, **I**nsertion loss, **R**eturn loss (4 coupler parameters)

### Common Mistakes
- Confusing excess loss with insertion loss
- Forgetting return loss (crosstalk) formula uses P₃/P₀

### 10-Second Revision
**Coupler splits/combines light. FBT = fused/twisted fibers. 4 parameters: CR, Excess, Insertion, Return loss.**

---

## Q 4.17 — Numerical: 2×2 Biconical Tapered Coupler *(Dec 23, 8 Marks)*

### Given
- P₀ = 200 mW (input), P₁ = 90 mW, P₂ = 85 mW, P₃ = 6.3 nW

### Solutions

**Coupling Ratio:**
$$CR = \frac{P_2}{P_1 + P_2} \times 100 = \frac{85}{90 + 85} \times 100 = \boxed{48.57\%}$$

**Excess Loss:**
$$= 10 \log\left(\frac{200 \times 10^{-3}}{175 \times 10^{-3}}\right) = \boxed{0.58 \text{ dB}}$$

**Insertion Loss (Port 0→1):**
$$= 10 \log\left(\frac{200}{90}\right) = \boxed{3.46 \text{ dB}}$$

**Insertion Loss (Port 0→2):**
$$= 10 \log\left(\frac{200}{85}\right) = \boxed{3.71 \text{ dB}}$$

**Return Loss (Crosstalk):**
$$= 10 \log\left(\frac{6.3 \times 10^{-9}}{200 \times 10^{-3}}\right) = \boxed{-75.01 \text{ dB}}$$

### Common Exam Mistakes
- Using P₁ in coupling ratio formula instead of P₂ (or vice versa)
- Not converting P₃ from nW to W
- Forgetting negative sign in return loss

---

## Q 4.18 — Optical Circulator *(4 Marks)*

### Definition
An **optical circulator** is a multiport non-reciprocal device that routes optical signals in a cyclic manner from one port to the next, allowing separation of forward and backward traveling signals.

### Diagram
**[Refer Diagram from PDF — Fig 1(a): 3-port, Fig 1(b): 4-port optical circulators]**

### Working Principle

#### 3-Port Circulator
- Port ① → Port ②
- Port ② → Port ③
- Port ③ → Port ①
- If light enters ① and reflects from ②: reflected light exits from ③ (NOT back into ①)

#### 4-Port Circulator
- Port ① → ② → ③ → ④ → ① (cyclic)

### Applications
- **Bidirectional communication** over single optical cable
- Building **optical add/drop elements** (with fiber Bragg gratings)
- Add and drop functionality in optical MUX/DEMUX

### Memory Trick
**"Circulator = Traffic Roundabout"** — enters at one junction, exits the next junction, never goes backward

---

## Q 4.19 — Compare Optical Isolator vs Circulator *(4 Marks)*

### Comparison Table

| Sr. No. | Parameter | Optical Isolator | Optical Circulator |
|---------|-----------|------------------|--------------------|
| 1 | Direction | One direction only | Between different ports |
| 2 | Ports | 2-port device | 3 or 4-port device |
| 3 | Usage | Isolate two ports | Separate optical powers traveling in opposite directions |
| 4 | Port Termination | Transmits forward without terminating | Any port can be terminated |
| 5 | Application | Prevent reflected light entering source | Build optical add/drop elements |
| 6 | Complexity | Simpler | More complex |
| 7 | Signal Routing | Blocks reverse signal | Routes reverse signal to different port |

### Memory Trick
**"2-port blocks, 3/4-port routes"**

### 10-Second Revision
**Isolator: 2-port, blocks reverse. Circulator: 3/4-port, routes reverse to next port.**

---

## Q 4.20 — Fiber Bragg Grating (FBG) *(Dec 23, Dec 24, 5–6 Marks)*

### Definition
A **Fiber Bragg Grating (FBG)** is a periodic structure written inside the fiber core that reflects a specific wavelength and passes all other wavelengths. Also called a **distributed Bragg reflector**.

### Diagram
**[Refer Diagram from PDF — Fig 1(a): FBG with circulator for optical add/drop]**

### How Gratings are Written in Fiber
1. Fiber made of silica doped with **germanium** → becomes **photosensitive**
2. **UV (ultraviolet) beams** illuminate fiber core
3. Radiation intensity varies periodically along fiber length
4. Where intensity is **low:** refractive index unchanged
5. Where intensity is **high:** refractive index increases
6. → Periodic variation in refractive index = **grating**
7. Short-period grating: period ≈ **0.5 μm** (comparable to wavelength)

### Working with Circulator
- Wavelengths λ₁, λ₂, λ₃, λ₄ enter Port ①
- Circulator routes all to Port ②
- FBG at Port ② reflects **only λ₂** (designed frequency)
- Reflected λ₂ → Port ③ (**DROPPED**)
- λ₁, λ₃, λ₄ pass through (transmitted)
- After grating, another circulator can **ADD** λ₂ back → output has λ₁, λ₂, λ₃, λ₄

### Advantages of Fiber Gratings
1. Very low losses — all-fiber device
2. Easily coupled with other fibers
3. Not sensitive to polarization
4. Low temperature coefficients
5. Simple packaging, low cost

### Important Exam Keywords
- Photosensitivity, Germanium doping, UV radiation, Distributed Bragg reflector, Periodic refractive index, Optical add/drop

### Memory Trick
**"FBG = Frequency-Selective Mirror in Fiber"** — reflects one λ, passes others

### Common Mistakes
- Saying FBG transmits the design wavelength — it **reflects** it
- Forgetting that germanium doping makes fiber photosensitive
- Not mentioning UV radiation as the writing mechanism

### 10-Second Revision
**FBG: Ge-doped fiber + UV light → periodic n variation → reflects one λ, transmits rest.**

---

## Q 4.21 — Optical Amplifiers: Working and Types *(May 23, 6 Marks)*

### Definition
**Optical amplifiers** amplify optical signals directly without optical-to-electrical conversion, providing gain in the optical domain.

### Types of Optical Amplifiers

| Type | Full Name |
|------|-----------|
| EDFA | Erbium Doped Fiber Amplifier |
| SOA | Semiconductor Optical Amplifier |
| FRA | Fiber Raman Amplifier |
| WFA | Wideband Fiber Amplifier |

### (1) EDFA — Erbium Doped Fiber Amplifier
- Erbium ions (Er³⁺) in fiber core absorb pump light and amplify signal
- Pump wavelengths: **980 nm** or **1480 nm**
- Signal wavelength: **1550 nm** (C-band)
- Optical insulator at output prevents back reflections

### (2) SOA — Semiconductor Optical Amplifier
- Based on InGaAsP laser diode operating **below threshold**
- Gain obtained in one pass through optical cavity
- Like a **Travelling Wave (TW) amplifier**

### (3) Raman Amplifiers (FRA)
- Based on **Stimulated Raman Scattering (SRS)**
- Atom in ground state absorbs photon → jumps to excited state
- Falls back → emits photon at **different energy/wavelength**
- Can amplify over very wide bandwidth

### (4) Wideband Fiber Amplifiers
- **Combination** of multiple amplifier types (serial, parallel, or series-parallel)
- Used for amplification over very wide wavelength range

### Materials Used for Active Medium in DFAs (Doped Fiber Amplifiers)
Rare-earth elements doped into glass fiber:
1. **Erbium (Er)** — for 1550 nm
2. **Neodymium (Nd)** — for 1060 nm
3. **Praseodymium (Pr)** — for 1310 nm

### Memory Trick
**"ESRW"** — **E**DFA, **S**OA, **R**aman, **W**ideband

### 10-Second Revision
**4 amplifiers: EDFA (best, 1550nm), SOA (compact), Raman (SRS), Wideband (combo). No O-E-O conversion.**

---

## Q 4.22 — Compare SOA vs EDFA *(May 24, 9 Marks)*

### Comparison Table

| Sr. No. | Parameter | SOA | EDFA |
|---------|-----------|-----|------|
| 1 | Working Principle | InGaAsP laser below threshold; gain in one pass (TW amplifier) | Er³⁺ ions excited by pump light; stimulated emission amplifies signal |
| 2 | Gain Medium | Semiconductor material | Erbium-doped silica fiber |
| 3 | Pumping Method | Electrical current injection | Optical pumping (980 nm or 1480 nm) |
| 4 | Maximum Gain | < 30 dB | > 50 dB |
| 5 | Gain at High Input | Unity | Unity (saturates) |
| 6 | Operating Wavelength | 1260–1650 nm (wide) | ~1550 nm (C-band) |
| 7 | Noise Figure | 7–10 dB | 4–6 dB (lower, better) |
| 8 | Polarization Sensitivity | High (problematic) | Low (better) |
| 9 | Non-linearity | Higher | Lower |
| 10 | Response Time | Fast | Slow |
| 11 | Power Consumption | Low | High |

### Memory Trick
**"EDFA > SOA in gain and noise. SOA > EDFA in speed and wavelength range."**

### 10-Second Revision
**EDFA: gain>50dB, low noise, 1550nm, optical pump. SOA: gain<30dB, compact, electrically pumped, faster.**

---

## Q 4.23 — EDFA in Detail *(Dec 24, 6 Marks)*

### Definition
An **Erbium Doped Fiber Amplifier (EDFA)** uses Er³⁺ ions in the fiber core as the gain medium. A pump laser excites erbium ions to higher energy states; the amplified signal is produced by **stimulated emission**.

### Diagram
**[Refer Diagram from PDF — Fig 1: Energy Level Diagram of Er³⁺ ions]**

### Block Diagram Components
1. **Weak input signal** (around 1550 nm)
2. **Pump laser** (980 nm or 1480 nm) — high power
3. **Wavelength Selective Coupler** — mixes signal + pump into Er³⁺ fiber
4. **Erbium Doped Fiber** — active medium where amplification occurs
5. **Optical Isolator** — at output, blocks back reflections

### Energy Level Transitions of Er³⁺ Ions

| Transition | Description |
|------------|-------------|
| 1 — Pump Transition | 980 nm pump excites Er³⁺ from ground → pump band |
| 2 — Non-radiative Decay | Mechanical vibrations → quick decay from pump band → metastable state |
| 3 — Pump (1480 nm) | 1480 nm photons excite Er³⁺ from ground → metastable state |
| 4 — Delay to lower state | Decay to lower state within metastable band |
| 5 — Spontaneous Emission | Some ions fall from metastable → ground (noise — ASE) |
| 6 — Stimulated Absorption | Ground state ions absorb external 1550 nm photons → metastable |
| 7 — Stimulated Emission | New photons (same energy, polarization) created at ~1530 nm → AMPLIFICATION |

### Key Wavelengths
- Pump: **980 nm** (preferred) or **1480 nm**
- Signal amplified: **1530–1565 nm** (C-band)
- Stimulated emission: ~**1530 nm**

### Important Exam Keywords
- Er³⁺ ions, Pump laser, Wavelength selective coupler, Metastable state, Stimulated emission, ASE (Amplified Spontaneous Emission)

### Memory Trick
**"PUMP → EXCITE → EMIT → AMPLIFY"**

### Common Mistakes
- Saying EDFA uses electrical pumping — it uses **optical pumping**
- Forgetting that optical isolator is placed at the output
- Confusing spontaneous emission (Transition 5 = noise/ASE) with stimulated emission (Transition 7 = useful amplification)

### 2-Minute Revision Notes
- EDFA: Er³⁺ fiber + pump (980/1480 nm) + wavelength coupler
- 7 energy transitions; Transition 7 = stimulated emission = amplification
- Operates at 1550 nm C-band
- Gain > 50 dB, noise figure 4–6 dB
- Output isolator prevents back-reflection

### 30-Second Revision
- Er³⁺ ions excited by pump light
- Metastable state = population inversion
- Incoming signal stimulates emission of identical photons
- Amplified output at 1530–1565 nm
- Optical isolator at output

### 10-Second Revision
**EDFA: 980nm pump excites Er³⁺ → stimulated emission amplifies 1550nm signal. Gain > 50dB.**

---
---

# QUICK REVISION TABLES

## Unit 3 — Key Formulas Summary

| Parameter | Formula | Units |
|-----------|---------|-------|
| Responsivity | R = ηλ/1.24 | A/W (λ in μm) |
| Responsivity | R = I_ph/P_inc | A/W |
| Quantum Efficiency | η = (electrons)/(photons) | — (0 to 1) |
| Long cut-off wavelength | λ_c = 1240/E_g | nm (E_g in eV) |
| Shot noise | I_shot = √(2qB(I_D+I_P)) | A |
| Thermal noise | I_thermal = √(4KTB/R) | A |
| SNR | S/N = I_P² / (I_thermal² + I_noise²·F_n) | dB |
| Avalanche gain | M = I_multiplied / I_primary | — |
| BER | BER = N_e / (B_t · t) | — |
| Si cutoff wavelength | λ_c = 1240/1.12 = 1107 nm | nm |

## Unit 4 — Key Formulas Summary

| Parameter | Formula | Notes |
|-----------|---------|-------|
| Loss (dB) | 10 log(P_out/P_in) | Negative for loss |
| Power budget | P_T = P_S − P_R | Must ≥ total loss |
| Total rise time | t_sys = √(t_tx²+t_mat²+t_mod²+t_rx²) | ns |
| NRZ bit rate | B = 0.70/t_sys | Mbit/s |
| RZ bit rate | B = 0.35/t_sys | Mbit/s |
| Receiver rise time | t_rx = 350/B_rx | ns (B_rx in MHz) |
| Coupling ratio | P₂/(P₁+P₂)×100 | % |
| Excess loss | 10 log(P₀/(P₁+P₂)) | dB |
| Insertion loss | 10 log(P₀/P₁) | dB |
| Return loss | 10 log(P₃/P₀) | dB |

## Quick Topic Map — Unit 3

| Topic | Key Point |
|-------|-----------|
| Photodetection | 3 steps: Absorption, Transport, Photocurrent |
| P-N diode | Reverse bias, narrow depletion, slower |
| PIN diode | Wider depletion, faster, lower capacitance |
| APD | Impact ionization, gain M≤200, high voltage |
| Quantum efficiency η | Carriers generated / photons incident |
| Responsivity R | R = ηλ/1.24 A/W |
| Thermal noise | 4KTB/R in resistors |
| Shot noise | 2qBI_D dark current |
| BER target | 10⁻⁹ to 10⁻¹² |

## Quick Topic Map — Unit 4

| Topic | Key Point |
|-------|-----------|
| P2P link | Source + Fiber + Detector |
| Power budget | P_allowed ≥ Total losses |
| Rise time budget | t_sys = √(sum of squares) |
| NRZ vs RZ | NRZ = 0.70/t, RZ = 0.35/t |
| WDM | Multiple λ on one fiber |
| OLT | Terminal with transponder + MUX/DEMUX |
| OADM | Add/drop individual wavelengths |
| OXC | Cross-connect for routing/switching |
| Optical isolator | Faraday 45°, blocks backward light |
| Optical circulator | Routes signal port1→2→3→1 |
| FBG | Reflects one λ, passes rest |
| EDFA | Er³⁺ + 980nm pump → gain at 1550nm |
| SOA | InGaAsP TW amplifier, electrically pumped |

---

## Expected University Question Bank

### Unit 3
1. Explain photodetection process with three steps. (Dec 23, 6M)
2. Compare P-N and P-I-N photodiodes from design perspective. (May 24, 6M)
3. Explain APD with construction, working, advantages. (Dec 23/24, 6M)
4. Compare PIN vs APD. (May 23, 6M)
5. Explain different noise types in photodetector. (Dec 24, 6M)
6. Define quantum efficiency and responsivity with equations. (Dec 23, 6M)
7. Numerical on quantum efficiency, responsivity, optical power.
8. Numerical on APD avalanche gain.
9. Numerical on SNR for PIN receiver.
10. Explain receiver structure. (Dec 24, 5M)

### Unit 4
1. Draw and explain point-to-point optical link. (May 23, 6M)
2. Explain power budget with equations and solve numerical. (May 24, Dec 23)
3. Explain rise time budget with equations and solve numerical. (May 24, Dec 23)
4. Explain WDM network architecture. (May 24, Dec 24)
5. Explain features of WDM architecture. (6M)
6. Explain optical isolator with Faraday effect. (Dec 23, Dec 24, 6M)
7. Explain optical couplers — Evanescent and FBT. (6M)
8. Numerical on 2×2 coupler parameters. (Dec 23, 8M)
9. Compare optical isolator and circulator. (4M)
10. Explain Fiber Bragg Grating with applications. (Dec 23, Dec 24)
11. Explain EDFA with energy level transitions. (Dec 24, 6M)
12. Compare SOA vs EDFA. (May 24, 9M)

---

*End of FOC Units 3 & 4 Complete Exam Notes*
*Prepared as per SPPU Sem 8 E&TC Syllabus*
*Based on classroom notes covering Dec 23, May 23, May 24, Dec 24 question papers*
