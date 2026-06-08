# UNIT : 5

---

# Important Questions Covered

1. Rayleigh Distribution — Properties, Mean and Variance (with Derivation)
2. Ricean Fading Channel Model — Explanation and Comparison with Rayleigh Fading
3. Non-Coherent Detection of FSK — Explanation with Block Diagram
4. Multipath Propagation with Diagram — ISI in Multipath Fading Channels
5. Compare Wideband and Narrowband Channels — Two Channel Models Each
6. Fading — Detailed Explanation and Classification of Types

---

# Q1. Rayleigh Distribution — Properties, Mean and Variance

## Introduction

The **Rayleigh distribution** is a probability distribution used to model the **envelope of a received signal** in a wireless channel where there is **no dominant line-of-sight (LOS) path** between transmitter and receiver. It arises naturally when the received signal is composed of **many reflected, scattered, and diffracted components** with random amplitudes and phases.

In mobile communications, Rayleigh fading is the standard model for **urban NLOS (Non-Line-of-Sight) environments**.

---

## Main Answer

### Physical Origin

Consider a received signal composed of **N multipath components**, each with random amplitude and phase:

```
r(t) = Σ aₙ · cos(2πfₙt + φₙ)
```

By the **Central Limit Theorem**, as N → ∞:
- The **in-phase component** (I) → Gaussian distributed: I ~ N(0, σ²)
- The **quadrature component** (Q) → Gaussian distributed: Q ~ N(0, σ²)

The **envelope** (amplitude) of the received signal:

```
r = √(I² + Q²)
```

The probability distribution of this envelope `r` follows the **Rayleigh distribution**.

---

### Probability Density Function (PDF)

The PDF of the Rayleigh distribution is:

```
         r        -r²
f(r) = ──── · exp(────)     for r ≥ 0
         σ²       2σ²

f(r) = 0                    for r < 0
```

Where:
- `r` = envelope amplitude (received signal amplitude)
- `σ²` = variance of each Gaussian component (I or Q) — the **modal parameter**
- `σ` = RMS value of the received voltage before envelope detection
- `e` = Euler's number (≈ 2.718)

---

### Cumulative Distribution Function (CDF)

The CDF gives the probability that the envelope `r` does not exceed a threshold `R`:

```
                    -R²
P(r ≤ R) = 1 - exp(────)
                    2σ²
```

This is used to compute **outage probability** in wireless systems.

---

### Derivation of Mean (Expected Value)

The mean of the Rayleigh distribution:

```
         ∞
E[r] = ∫  r · f(r) dr
         0

         ∞    r²        -r²
     = ∫  ──── · exp(────) dr
         0    σ²        2σ²
```

**Substitution:** Let `u = r²/(2σ²)` → `r = √(2σ²u)` → `dr = σ²/r · du` → `r·dr = σ² du`

After substituting and applying the Gamma function identity: `Γ(3/2) = √π/2`

```
              ∞
E[r] = (1/σ²) ∫  r² · exp(-r²/2σ²) dr
              0

     = σ · √(π/2)
```

**∴ Mean = E[r] = σ√(π/2) ≈ 1.2533σ**

---

### Derivation of Second Moment (E[r²])

```
         ∞
E[r²] = ∫  r² · f(r) dr
         0

         ∞    r³        -r²
      = ∫  ──── · exp(────) dr
         0    σ²        2σ²
```

Using substitution `u = r²/(2σ²)` and Gamma identity `Γ(2) = 1`:

```
E[r²] = 2σ²
```

This represents the **mean power** of the received signal.

---

### Derivation of Variance

```
Var(r) = E[r²] - [E[r]]²

       = 2σ² - [σ√(π/2)]²

       = 2σ² - σ²·(π/2)

       = σ²(2 - π/2)
```

**∴ Variance = σ²(2 - π/2) ≈ 0.4292σ²**

---

### Summary of Key Formulas

| Parameter | Formula | Approximate Value |
|---|---|---|
| **PDF** | f(r) = (r/σ²)·exp(−r²/2σ²) | — |
| **CDF** | P(r≤R) = 1 − exp(−R²/2σ²) | — |
| **Mean** | E[r] = σ√(π/2) | ≈ 1.2533σ |
| **Second Moment** | E[r²] = 2σ² | Mean power |
| **Variance** | Var(r) = σ²(2 − π/2) | ≈ 0.4292σ² |
| **Mode (peak of PDF)** | r_mode = σ | Peak at r = σ |
| **Median** | r_median = σ√(2·ln2) | ≈ 1.1774σ |

---

### Properties of Rayleigh Distribution

1. **Non-Negative Support** — `f(r) = 0` for `r < 0`; only defined for positive amplitudes.
2. **Unimodal** — PDF has a single peak (mode) at `r = σ`.
3. **Right-Skewed** — Distribution has a longer right tail; mean > mode.
4. **Parameter σ Controls Shape** — Increasing σ shifts and spreads the distribution; larger σ = stronger average signal.
5. **Mean Power = 2σ²** — The average received power equals twice the Gaussian variance.
6. **NLOS Condition** — Valid when there is NO dominant LOS component; purely scattered signal.
7. **Special Case of Ricean** — Rayleigh = Ricean with K-factor = 0 (zero LOS component).
8. **Outage Probability** — CDF directly gives probability of signal below threshold (outage).

---

## Diagram

```
RAYLEIGH PDF: f(r) = (r/σ²)·exp(−r²/2σ²)

f(r)
 │
 │           ___
 │         /     \
 │        /       \
 │       /         \
 │      /           \
 │     /             \           σ₁ < σ₂ < σ₃
 │    /               \___
 │   /                     \___
 │  /                           \___________
 │ /                                         \____
 └───────────────────────────────────────────────→ r
   0    σ   2σ   3σ   4σ

   Peak (Mode) at r = σ
   Mean = σ√(π/2) ≈ 1.25σ  (to the right of peak)

CHANNEL MODEL (Physical Basis):

Transmitter ──→ [Wall/Building]──→ path 1 ──→
                                              → Σ → Received Envelope r (Rayleigh)
           ──→ [Ground]──────────→ path 2 ──→
           ──→ [Car/Object]──────→ path 3 ──→
           ──→ [Lamppost]────────→ path 4 ──→

  Each path: random amplitude + random phase
  Sum of many: I,Q → Gaussian → Envelope → Rayleigh
```

*Figure: Rayleigh PDF Shape and Physical Multipath Origin*

---

## Example

**Given:** A wireless channel with σ = 1 V

- Mean received amplitude = σ√(π/2) = 1 × √(1.5708) = **1.2533 V**
- Mean power = 2σ² = 2 × 1 = **2 W**
- Variance = σ²(2 − π/2) = 1 × (2 − 1.5708) = **0.4292 V²**
- Probability that amplitude falls below 1V:
  P(r ≤ 1) = 1 − exp(−1/2) = 1 − 0.6065 = **0.3935 (39.35%)**

---

## Conclusion

The **Rayleigh distribution** is the cornerstone model for **NLOS mobile fading channels**. Its PDF `f(r) = (r/σ²)·exp(−r²/2σ²)` leads to a mean of `σ√(π/2)` and variance of `σ²(2 − π/2)`. It directly enables calculation of **outage probability and fade margins** in wireless system design.

---

# Q2. Ricean Fading Channel Model — Explanation and Comparison with Rayleigh

## Introduction

The **Ricean (Rice) fading model** describes a wireless channel where, in addition to multiple scattered and reflected components, there exists a **dominant Line-of-Sight (LOS) path** between transmitter and receiver. This direct path carries significant power and prevents the signal amplitude from going to zero as frequently as in Rayleigh fading. The Ricean model was proposed by **Stephen O. Rice** and is common in **suburban, indoor, and satellite communication channels**.

---

## Main Answer

### Physical Origin of Ricean Fading

Received signal = **one strong LOS component + many scattered components**

```
r(t) = A·cos(2πfct + θ) + Σ aₙ·cos(2πfₙt + φₙ)
       └─── LOS component ───┘  └──── scattered ─────┘
```

- LOS component has fixed amplitude `A` and phase `θ`.
- Scattered components → in-phase I and quadrature Q → both Gaussian but with **non-zero mean**.
- The envelope of the combined signal follows the **Ricean distribution**.

---

### Ricean PDF

```
         r        -(r² + A²)      (rA)
f(r) = ──── · exp(──────────) · I₀(──)     for r ≥ 0
         σ²          2σ²           σ²
```

Where:
- `r` = envelope amplitude
- `A` = amplitude of the dominant LOS component
- `σ²` = variance of scattered components (each I or Q Gaussian)
- `I₀(·)` = **modified Bessel function of the first kind, zero order** — accounts for the LOS component

---

### The K-Factor (Ricean K-Factor)

The **K-factor** (also called the Ricean factor) is the most important parameter:

```
     Power of LOS component      A²
K = ─────────────────────── = ──────
     Power of scattered         2σ²
     components
```

- `K = 0` → A = 0 → **No LOS component → Reduces to Rayleigh distribution**
- `K → ∞` → Dominant LOS, no fading → **AWGN channel** (no multipath fading)
- Typical values: K = 1 to 30 dB depending on environment

In dB: `K_dB = 10·log₁₀(K)`

---

### Ricean PDF in Terms of K

Substituting K:

```
                 -(r² + 2Kσ²)         (r√(2K))
f(r) = (2r(K+1)/Ω) · exp(──────────) · I₀(──────────)
                                Ω            √(Ω/(K+1))
```

Where `Ω = 2σ² + A²` = total mean power.

As `K → 0`: Ricean → **Rayleigh** (no LOS)
As `K → ∞`: Ricean → **Gaussian** (pure LOS, AWGN)

---

### Properties of Ricean Distribution

1. **LOS Component Present** — Non-zero mean of I and Q components due to direct path.
2. **Envelope Never Goes to Zero** — Unlike Rayleigh, signal amplitude has a non-zero floor due to LOS.
3. **K-Factor Controls Severity** — Higher K = stronger LOS = less fading = better channel.
4. **Generalizes Rayleigh** — Rayleigh is a special case when K = 0.
5. **Less Severe Fading** — Deep fades are less frequent than Rayleigh.
6. **PDF Peak Shifts Right** — As K increases, PDF peak moves toward `A` (LOS amplitude).
7. **Bessel Function** — Presence of `I₀` is the mathematical signature of a LOS component.

---

## Comparison: Rayleigh vs Ricean Fading

| Parameter | Rayleigh Fading | Ricean Fading |
|---|---|---|
| **LOS Component** | ❌ None — only scattered paths | ✅ Present — dominant LOS path exists |
| **K-Factor** | K = 0 (by definition) | K > 0 (ranges from 1 to 30+ dB) |
| **PDF** | f(r) = (r/σ²)·exp(−r²/2σ²) | f(r) = (r/σ²)·exp(−(r²+A²)/2σ²)·I₀(rA/σ²) |
| **In-Phase (I), Quadrature (Q)** | Both zero-mean Gaussian | Non-zero mean Gaussian (due to LOS) |
| **Fading Severity** | More severe — deep fades frequent | Less severe — LOS prevents very deep fades |
| **Typical Environment** | Dense urban NLOS, urban canyons | Suburban, indoor, satellite, rural LOS |
| **Signal Envelope at Zero** | f(0) = 0 but can come close | Probability of near-zero is much lower |
| **Special Case** | Special case of Ricean (K=0) | Generalizes Rayleigh (K→0 = Rayleigh) |
| **Mathematical Complexity** | Simpler (no Bessel function) | More complex (Bessel function I₀) |
| **BER Performance** | Worse (more fading) | Better (LOS improves SNR) |
| **Application** | Urban mobile, NLOS links | Indoor Wi-Fi, satellite, LOS microwave |

---

## Diagram

```
RAYLEIGH vs RICEAN PDF COMPARISON

f(r)
 │
 │   Ricean (K=large)
 │          │
 │          │ ___
 │          │/   \                   (narrow, near A)
 │         /│     \
 │        / │      \
 │  Ricean  │  (K=small)
 │     ___  │
 │    /   \_│___
 │   /       \   \___
 │  /         \      \___
 │ Rayleigh    \          \___
 │/─────────────\──────────────→ r
 0              A            3A

 K=0 (Rayleigh): PDF peaks near 0, heavy tail
 K>0 (Ricean): PDF shifts right, peak near A (LOS amplitude)
 K=∞ (AWGN): Very narrow peak at r = A


PHYSICAL CHANNEL COMPARISON:

RAYLEIGH:
Tx ──→ [scatter]──→ path 1 ──→
    ──→ [scatter]──→ path 2 ──→  Σ → Rx
    ──→ [scatter]──→ path 3 ──→
    (NO direct path)

RICEAN:
Tx ══════════════════════════════> Rx  (STRONG LOS, amplitude A)
    ──→ [scatter]──→ path 1 ──→
    ──→ [scatter]──→ path 2 ──→  Σ → Rx  (scattered components)
```

*Figure: Rayleigh vs Ricean PDF and Channel Models*

---

## Example

**Indoor Wi-Fi (Ricean, K = 6 dB = 4):**
- LOS path exists between router and laptop.
- K = 4: LOS power = 4× scattered power.
- Fading is mild; signal stays strong most of the time.
- BER is lower than an equivalent Rayleigh channel.

**Urban cellular (Rayleigh, K = 0):**
- No LOS between base station and phone (buildings block direct path).
- All received components are scattered → Rayleigh envelope.
- Deep fades occur; outage events are more frequent.

---

## Conclusion

**Ricean fading** is the appropriate model when a **LOS component** exists alongside scattered components. The **K-factor** quantifies the LOS dominance: as K increases, the channel improves from severe Rayleigh fading toward an AWGN-like channel. For SPPU exams, the critical comparison point is: **Rayleigh = no LOS (K=0), Ricean = LOS present (K>0)**.

---

# Q3. Non-Coherent Detection of FSK — Explanation with Block Diagram

## Introduction

**Non-coherent detection** is a signal detection method that does **not require knowledge of the carrier phase** at the receiver. Unlike coherent detection (which needs a phase-synchronized reference), non-coherent detection uses the **signal envelope** (amplitude) for decision making. It is simpler to implement but has slightly worse BER performance than coherent detection.

**FSK (Frequency Shift Keying)** represents binary data by switching between **two different frequencies** (f₁ for bit '1', f₂ for bit '0'). Non-coherent FSK detection is one of the most commonly implemented demodulation schemes in wireless systems.

---

## Main Answer

### Why Non-Coherent?

In wireless channels:
- The received signal undergoes random **phase shifts** due to multipath propagation.
- Estimating and tracking the carrier phase requires a **Phase-Locked Loop (PLL)** — complex and expensive.
- Non-coherent detection avoids phase estimation entirely.
- Ideal for **FSK** since information is in **frequency** (not phase).
- Used in **DECT, paging systems, Bluetooth** (GFSK).

---

### Binary FSK Signal Model

**Transmitted signal:**
```
s₁(t) = A·cos(2πf₁t)    (bit '1', frequency f₁)
s₀(t) = A·cos(2πf₀t)    (bit '0', frequency f₀)
```

**Received signal (with phase shift φ due to channel):**
```
r(t) = A·cos(2πfᵢt + φ) + n(t)
```
where n(t) = AWGN noise, φ = unknown random phase.

**Non-coherent detection ignores φ** — uses envelope only.

---

### Non-Coherent FSK Detector — Block by Block

The receiver has **two parallel branches** — one tuned to f₁, one to f₀. The branch with the **larger envelope output** wins.

#### Block 1 — Bandpass Filter (BPF)

- **Upper branch BPF:** Centered at f₁ — passes components near f₁, rejects f₀ and noise outside band.
- **Lower branch BPF:** Centered at f₀ — passes components near f₀, rejects f₁ and noise outside band.
- Output: Bandlimited signal containing only the relevant frequency component + narrowband noise.

#### Block 2 — Envelope Detector (Squarer + LPF + Square Root, or Rectifier + LPF)

Two implementation variants:

**Variant A — Squarer Method:**
```
BPF output → [Square: (·)²] → [Low Pass Filter] → [√·] → Envelope
```

**Variant B — Rectifier Method (approximation):**
```
BPF output → [Full-wave Rectifier] → [Low Pass Filter] → Envelope
```

The envelope detector extracts **amplitude** `|r(t)|` — the envelope of the filtered signal.

- For the branch matching the transmitted frequency: large envelope value.
- For the non-matching branch: small envelope value (just noise).

#### Block 3 — Sampler (at optimal sampling instant)

- At the **end of each symbol period T**, the envelope output is sampled.
- Produces scalar values E₁ (from f₁ branch) and E₀ (from f₀ branch).

#### Block 4 — Comparator (Decision Device)

```
If E₁ > E₀ → decide bit '1' was transmitted
If E₀ > E₁ → decide bit '0' was transmitted
```

Simple threshold comparison — no phase reference needed.

---

## Block Diagram

```
NON-COHERENT DETECTION OF BINARY FSK

                    ┌─────────────────────────────────────────────┐
                    │          UPPER BRANCH (for bit '1')         │
                    │                                             │
                    │  ┌──────────┐  ┌──────────┐  ┌─────────┐  │
Received  ─────────>├──┤  BPF at  ├─>┤ Envelope ├─>┤ Sample  ├──┤── E₁
signal r(t)         │  │    f₁    │  │ Detector │  │  at T   │  │   │
                    │  └──────────┘  └──────────┘  └─────────┘  │   │
                    │                                             │   │
                    │                                             │   ▼
                    │                                             │ ┌──────────┐
                    │                                             │ │Comparator│──> Decision
                    │                                             │ │ E₁ vs E₀ │   (bit '0'
                    │                                             │ └──────────┘    or '1')
                    │                                             │   ▲
                    │  ┌──────────┐  ┌──────────┐  ┌─────────┐  │   │
                    ├──┤  BPF at  ├─>┤ Envelope ├─>┤ Sample  ├──┤── E₀
                    │  │    f₀    │  │ Detector │  │  at T   │  │
                    │  └──────────┘  └──────────┘  └─────────┘  │
                    │          LOWER BRANCH (for bit '0')        │
                    └─────────────────────────────────────────────┘


ENVELOPE DETECTOR (Detail):

         ┌────────────┐    ┌───────────────┐    ┌────────────┐
BPF  ───>│   Square   ├───>│ Low Pass      ├───>│   Square   ├──> Envelope
output   │   (·)²     │    │ Filter (LPF)  │    │   Root √·  │
         └────────────┘    └───────────────┘    └────────────┘


SIGNAL WAVEFORMS:

Bit '1' transmitted (f₁):

  BPF at f₁ output: ────/\/\/\/\────  (large amplitude — correct branch)
  Envelope at f₁:   ─────────────     (high value E₁)

  BPF at f₀ output: ────noise──────  (small — no signal at f₀)
  Envelope at f₀:   ─────────────     (low value E₀)

  E₁ > E₀ → Comparator decides '1' ✓


DECISION RULE:
  E₁ > E₀  →  bit '1'
  E₀ > E₁  →  bit '0'
```

*Figure: Non-Coherent FSK Detection — Dual-Branch Envelope Detector*

---

### BER of Non-Coherent FSK

```
         1      -Eb
BER = ─── · exp(──── )
         2       2N₀

Where:
  Eᵦ = energy per bit
  N₀ = noise power spectral density
```

This is **approximately 3 dB worse** than coherent FSK at the same Eᵦ/N₀ — the cost of not knowing the phase.

---

### Advantages of Non-Coherent Detection

1. **No Phase Synchronization Required** — No PLL or carrier phase recovery circuit needed.
2. **Simpler Receiver Design** — Fewer components; lower cost and complexity.
3. **Faster Acquisition** — No lock-time for phase recovery; suitable for burst data.
4. **Robust to Phase Instability** — Works in channels with rapid phase variations.
5. **Ideal for FSK** — FSK encodes information in frequency, not phase — phase info is unnecessary.
6. **Lower Power Consumption** — Simpler circuitry uses less power; suitable for IoT/battery devices.

### Disadvantages of Non-Coherent Detection

1. **BER Performance Loss** — ~3 dB penalty compared to coherent detection at same Eᵦ/N₀.
2. **Not Suitable for Phase Modulation** — Cannot detect PSK, QAM where phase carries information.
3. **Noise Sensitivity** — Envelope detectors square the noise too; noise×noise term (non-linear) degrades performance at low SNR.
4. **Bandwidth Efficiency** — FSK itself is less bandwidth-efficient than PSK/QAM.

---

## Example

**Bluetooth Classic (BR mode):**
- Uses GFSK (Gaussian Frequency Shift Keying) with non-coherent detection.
- Bit '1' → +160 kHz deviation; bit '0' → −160 kHz deviation.
- Envelope detector in each branch → comparator → recovered data.
- No phase tracking required; simple radio design at 2.4 GHz.

---

## Conclusion

**Non-coherent FSK detection** uses two parallel **BPF + Envelope Detector** branches, one for each FSK frequency, and decides the bit by comparing envelope amplitudes. It sacrifices approximately **3 dB of SNR** compared to coherent detection but eliminates the complexity of **carrier phase recovery** — making it the preferred approach for low-cost, low-power wireless devices.

---

# Q4. Multipath Propagation with Diagram — ISI in Multipath Fading Channels

## Introduction

**Multipath propagation** occurs when a transmitted signal reaches the receiver via **multiple paths** due to **reflection, diffraction, and scattering** off buildings, terrain, vehicles, and other objects. Each path has a different **time delay, amplitude, and phase**, causing the multiple copies of the signal to arrive at the receiver at different times. This is the primary cause of **fading** in wireless communications.

---

## Main Answer

### Mechanisms of Multipath Propagation

#### 1. Reflection

- Occurs when signal hits a surface **large compared to wavelength** (buildings, hills, ground).
- Part of the wave is reflected at an angle equal to the angle of incidence.
- Reflected path travels a **longer distance** → arrives later than direct path.
- Can cause **constructive or destructive** interference at receiver.

#### 2. Diffraction

- Occurs when signal encounters a **sharp edge or obstruction** (building corner, hilltop).
- Signal bends around the obstacle → propagates into the **shadow region**.
- Explains why signals are received even when no LOS exists.
- Amplitude reduced compared to direct path.

#### 3. Scattering

- Occurs when signal hits objects **small compared to wavelength** (lamp posts, signs, foliage, rain).
- Signal energy is **scattered in many directions** — creates multiple weak paths.
- Dominant in urban environments with many small objects.
- Creates the many scattered components modeled by the **Rayleigh distribution**.

---

### Channel Impulse Response

The multipath channel can be modeled as a **time-varying linear filter** with impulse response:

```
        N-1
h(τ) = Σ  aₙ · δ(τ - τₙ) · exp(jφₙ)
        n=0

Where:
  aₙ  = amplitude of nth multipath component
  τₙ  = time delay of nth component
  φₙ  = phase shift of nth component
  N   = number of multipath components
```

The **power delay profile** shows how received power is distributed over delays τ.

---

### What is ISI (Inter-Symbol Interference)?

**ISI (Inter-Symbol Interference)** occurs when **delayed copies of one symbol overlap with the next symbol** at the receiver, causing the later-arriving copies to corrupt the detection of the following symbol.

**Condition for ISI:**
```
If  τmax  >  Ts (symbol duration)  →  ISI occurs

Where:
  τmax = maximum excess delay (longest path minus shortest path)
  Ts   = symbol period
```

**No ISI:** τmax < Ts — all echoes arrive within the current symbol period.
**ISI occurs:** τmax > Ts — echoes from symbol 1 spill into symbol 2's detection window.

**Effect of ISI:**
- **BER increases** dramatically even at high SNR (irreducible error floor).
- **Equalizers** (MLSE, DFE) or **OFDM** (converts wideband to narrowband subcarriers) are used to mitigate ISI.

---

## Diagram

```
MULTIPATH PROPAGATION — PHYSICAL PATHS

                          ┌─────────────┐
                          │  Building 1 │
                          │             │
                          └─────────────┘
                         ↗ (Reflection path 1: delay τ₁)
    ┌──────────┐       ↗                         ┌──────────┐
    │Transmitter│─────────────────────────────────│ Receiver │
    │    (Tx)   │──────────────────────────────>──│   (Rx)   │
    └──────────┘  Direct LOS path (delay τ₀)     └──────────┘
         │       ↘                               ↗
         │        ↘  ┌─────────────┐           ↗
         │         ↘─│  Building 2 │──────────↗ (Reflection path 2: delay τ₂)
         │           └─────────────┘
         │                                    ↗
         └──→ [Lamppost] ─ (Scatter) ────────↗  (Scattered path 3: delay τ₃)

RECEIVED SIGNAL:
  r(t) = a₀·s(t-τ₀) + a₁·s(t-τ₁) + a₂·s(t-τ₂) + a₃·s(t-τ₃) + noise


POWER DELAY PROFILE:
Power
  │
  │   █                          (direct path, highest power)
  │   █
  │   █    █                     (1st echo, reflected)
  │         █
  │              █               (2nd echo, reflected+scattered)
  │                   █          (3rd echo, weakest)
  └───────────────────────────→ Delay τ
      τ₀   τ₁   τ₂   τ₃
      ← τmax (maximum excess delay) →


ISI EFFECT ON SYMBOLS:

WITHOUT ISI (τmax < Ts):
  Symbol 1: ████████████████
  Symbol 2:                  ████████████████
  Echoes:   ████(echo 1)████(echo 2)
  → All echoes arrive within Symbol 1 period → NO ISI

WITH ISI (τmax > Ts):
  Symbol 1: ████████████████
  Symbol 2:                  ████████████████
  Echo of 1:         ──────────ECHO───────────>
                               ↑ spills into Symbol 2 period!
  → Receiver tries to detect Symbol 2, but echo of Symbol 1 adds!
  → ISI! → BER increases!
```

*Figure: Multipath Propagation Paths and ISI Effect on Symbol Detection*

---

### Effects of Multipath Propagation

| Effect | Description |
|---|---|
| **Rayleigh Fading** | Random amplitude variation due to constructive/destructive interference of multiple paths |
| **ISI** | Delayed copies of symbols corrupt subsequent symbols |
| **Doppler Spread** | Moving transmitter/receiver causes frequency shift; paths from different angles = different Doppler |
| **Coherence Bandwidth** | Related to delay spread; channel is flat only within coherence bandwidth |
| **Delay Spread** | RMS spread of arrival times of multipath components |

---

### ISI Mitigation Techniques

1. **Equalizers** — MLSE (Viterbi), DFE, LMS — remove ISI by estimating and subtracting echoes.
2. **OFDM** — Converts wideband channel into many flat narrowband subchannels, each narrower than coherence bandwidth.
3. **Cyclic Prefix (CP)** — Guard interval in OFDM absorbs multipath delay; converts ISI into benign phase rotation.
4. **Rake Receiver** — Combines multiple delayed copies constructively (used in CDMA systems).
5. **Spread Spectrum (CDMA)** — Wider bandwidth resolves individual multipath components.

---

## Conclusion

**Multipath propagation** is the fundamental channel challenge in wireless communications — signals arrive via reflected, diffracted, and scattered paths, creating **random fading** and **ISI**. ISI occurs when the maximum excess delay exceeds the symbol period, creating an irreducible error floor. Modern systems combat this with **OFDM, cyclic prefix, and adaptive equalizers**.

---

# Q5. Compare Wideband and Narrowband Channels — Two Channel Models Each

## Introduction

Wireless channels are classified as **narrowband** or **wideband** based on the relationship between the **signal bandwidth** and the **coherence bandwidth** of the channel. This classification determines whether the channel introduces **flat fading or frequency-selective fading** and guides the choice of **channel model** for system design.

---

## Main Answer

### Key Relationship: Signal BW vs Coherence Bandwidth

```
Coherence Bandwidth Bc ≈ 1 / (5 · σ_τ)

Where σ_τ = RMS delay spread of the channel

If Signal Bandwidth Bs << Bc  →  NARROWBAND (Flat Fading)
If Signal Bandwidth Bs >> Bc  →  WIDEBAND  (Frequency-Selective Fading)
```

---

### Narrowband Channels

#### Definition

A **narrowband channel** has a signal bandwidth **much smaller than the coherence bandwidth**. All frequency components of the signal experience the **same fading** — the channel appears flat across the signal's bandwidth.

#### Characteristics

- **Flat fading** — entire signal spectrum fades together.
- Single-tap channel model — one complex gain models the entire channel.
- **No ISI** within the signal band (delay spread << symbol duration).
- Channel modeled as a single complex multiplier: `r(t) = h·s(t) + n(t)`
- Envelope of received signal follows **Rayleigh** (NLOS) or **Ricean** (LOS) distribution.
- Example systems: **narrowband GSM voice channels, paging systems**.

#### Two Narrowband Channel Models

**1. AWGN (Additive White Gaussian Noise) Channel Model:**
- Simplest model: no fading, only thermal noise.
- `r(t) = s(t) + n(t)` where n(t) = white Gaussian noise.
- BER is determined purely by Eᵦ/N₀.
- Used for link budget analysis; baseline performance benchmark.
- Does **not** model multipath — ideal channel.

**2. Rayleigh Flat Fading Channel Model:**
- Single complex gain `h` that varies according to Rayleigh distribution.
- `r(t) = h·s(t) + n(t)` where `|h|` ~ Rayleigh.
- Models **NLOS narrowband channels** (urban cellular, 2G GSM voice).
- Clarke's model generates the Rayleigh-distributed envelope with Doppler spectrum.
- Used for BER analysis of modulation schemes in mobile channels.

---

### Wideband Channels

#### Definition

A **wideband channel** has a signal bandwidth **much larger than the coherence bandwidth**. Different frequency components experience **different fading** — the channel is frequency-selective. Multiple resolvable multipath components exist.

#### Characteristics

- **Frequency-selective fading** — different parts of the spectrum fade differently.
- Multi-tap channel model — multiple delayed versions of signal superpose.
- **ISI** is present — delay spread > symbol period.
- Channel modeled as FIR filter: `r(t) = Σ hₙ·s(t−nTs) + n(t)`
- Used in broadband systems: **4G LTE, 5G NR, 802.11n/ac/ax Wi-Fi**.

#### Two Wideband Channel Models

**1. Saleh-Valenzuela (SV) Model:**
- Developed for **indoor wideband channels** (IEEE 802.11, UWB).
- Models multipath arrivals in **clusters**: paths arrive in groups (clusters), not individually.
- Within each cluster, paths arrive according to a Poisson process.
- Cluster and ray arrival rates (Λ and λ), amplitude decay modeled by exponential decay.
- Used for: **UWB (Ultra-Wideband), 60 GHz mmWave, indoor Wi-Fi channel modeling**.
- Standard reference: IEEE 802.11 channel model uses SV as foundation.

**2. COST 207 Model:**
- Developed by **COST (European Cooperation in Science and Technology) Project 207**.
- Models **outdoor wideband cellular channels** for GSM and 3G systems.
- Defines standard **delay power profiles** for 4 environments:
  - **Rural Area (RA):** Short delay spread, 1–2 taps
  - **Typical Urban (TU):** Moderate delay spread, ~6 taps
  - **Bad Urban (BU):** Long delay spread, strong echoes, ~12 taps
  - **Hilly Terrain (HT):** Very long delays from distant hills, ~12 taps
- Used for: **GSM, GPRS, 3G UMTS system design and simulation**.
- Standardized by **ETSI** for cellular simulation.

---

## Comparison Table: Narrowband vs Wideband Channels

| Parameter | Narrowband Channel | Wideband Channel |
|---|---|---|
| **Signal Bandwidth** | Bs << Bc (coherence BW) | Bs >> Bc (coherence BW) |
| **Fading Type** | **Flat fading** — uniform across spectrum | **Frequency-selective fading** — varies with frequency |
| **Coherence Bandwidth** | Bc >> signal bandwidth | Bc << signal bandwidth |
| **Delay Spread** | Small (σ_τ << Ts) | Large (σ_τ >> Ts) |
| **ISI** | ❌ None | ✅ Present (major concern) |
| **Channel Model Taps** | Single tap (one complex gain h) | Multiple taps (FIR filter model) |
| **Channel Impulse Response** | Flat (single delta function) | Multiple delayed delta functions |
| **Typical Systems** | 2G GSM voice, paging, narrowband IoT | 4G LTE, 5G NR, Wi-Fi (802.11n/ac/ax) |
| **Channel Models** | AWGN, Rayleigh flat fading | Saleh-Valenzuela, COST 207 |
| **Equalization Needed** | No | Yes (OFDM, DFE, MLSE) |
| **Bandwidth** | Typically < 200 kHz | Typically > 1 MHz |
| **BER Sensitivity** | SNR-limited | Delay spread + SNR limited |

---

## Diagram

```
NARROWBAND vs WIDEBAND — FREQUENCY DOMAIN VIEW

NARROWBAND (Flat Fading):              WIDEBAND (Frequency-Selective):

|H(f)|                                 |H(f)|
  │                                       │    ___
  │                                       │   /   \       ___
  │ ─────────────────── ← H(f) flat       │__/     \     /   \___
  │                                       │         \___/
  │                                       │
  └──────────────────────→ f             └────────────────────→ f
      │←── Signal BW ──→│                    │←─── Signal BW ───→│
      │←──────── Bc ──────────────→│         │←Bc→│
      Signal BW << Bc               Signal BW >> Bc
      All freqs fade same           Different freqs fade differently


DELAY PROFILE COMPARISON:

Narrowband:                            Wideband:
  Power                                 Power
    │ █                                   │ █
    │                                     │      █
    │                                     │           █
    └──→ delay                            └────────────→ delay
  (one strong path)                     (many resolvable paths)

  τmax < Ts → no ISI                    τmax > Ts → ISI!
```

*Figure: Narrowband (Flat Fading) vs Wideband (Frequency-Selective) Channel Characteristics*

---

## Conclusion

The **narrowband vs wideband classification** is fundamental to wireless system design. Narrowband channels are simple to model (AWGN or Rayleigh) but inefficient for high data rates. Wideband channels support high throughput but require sophisticated **ISI mitigation** through OFDM and advanced channel models like **Saleh-Valenzuela and COST 207**.

---

# Q6. Fading — Detailed Explanation and Classification of Types

## Introduction

**Fading** is the variation in the **amplitude, phase, or multipath delay** of a received wireless signal over time, distance, or frequency. It is caused by the destructive and constructive interference of multiple signal components arriving via different paths, and by **shadowing** due to large obstacles. Fading is the primary impairment in wireless channel design and directly determines system **BER, coverage, and capacity**.

---

## Main Answer

### Fading Classification — Overview

```
                          FADING
                            │
           ┌────────────────┴────────────────┐
           │                                 │
    LARGE-SCALE FADING                SMALL-SCALE FADING
   (distance-dependent)             (rapid, local variation)
           │                                 │
    ┌──────┴──────┐              ┌───────────┴───────────┐
    │             │              │                       │
Path Loss    Shadowing      Due to TIME              Due to DOPPLER
(slow decay) (log-normal)   SPREADING            (time variance)
                                │                       │
                         ┌──────┴──────┐        ┌───────┴───────┐
                         │             │        │               │
                       FLAT    FREQUENCY     FAST           SLOW
                      FADING    SELECTIVE   FADING          FADING
                               FADING
```

*Figure: Complete Fading Classification Tree*

---

### 1. Large-Scale Fading

Large-scale fading describes signal variation over **large distances** (hundreds of meters to kilometers). It is **slow** — changes only as the mobile moves significantly.

#### 1a. Path Loss (Free-Space and Log-Distance)

- Signal power decreases with **distance** due to **geometric spreading** of the wavefront.
- **Free-Space Path Loss:**
  ```
  PL(d) = 20·log₁₀(4πd/λ)   [dB]
  ```
- **Log-Distance Path Loss Model:**
  ```
  PL(d) = PL(d₀) + 10n·log₁₀(d/d₀)   [dB]
  ```
  Where `n` = path loss exponent (n=2 free space, n=3-4 urban).
- Deterministic and predictable from transmitter-receiver distance.

#### 1b. Shadowing (Log-Normal Fading)

- Caused by **large obstacles** (hills, buildings) blocking or attenuating the signal.
- Signal power variation follows a **log-normal distribution** (Gaussian in dB).
- **Slow variation** — changes as mobile moves around buildings.
- Modeled by adding a zero-mean Gaussian random variable X_σ (in dB) to path loss:
  ```
  PL(d) = PL(d₀) + 10n·log₁₀(d/d₀) + Xσ
  ```
  Where Xσ ~ N(0, σ²_shadowing), typical σ = 6–12 dB.
- Also called **slow fading** (distinguished from small-scale fast fading).

---

### 2. Small-Scale Fading

Small-scale fading describes **rapid amplitude and phase variations** of the received signal over **very short distances** (on the order of wavelength, ~centimeters) or **short time intervals** (milliseconds). Caused by multipath propagation.

Two independent dimensions of classification:

---

#### Dimension 1 — Based on Multipath TIME SPREADING (Delay Spread vs Symbol Period)

This determines whether ISI occurs.

##### 2a. Flat Fading (Narrowband Fading)

- **Condition:** `Bs << Bc` OR `σ_τ << Ts` (delay spread << symbol period)
- Channel **bandwidth > signal bandwidth** — entire signal fits within flat part of channel.
- All frequency components fade **equally and simultaneously**.
- **No ISI** — all echoes arrive within one symbol period.
- Channel modeled as **single complex multiplier** h(t): `r(t) = h(t)·s(t) + n(t)`
- Envelope follows Rayleigh (NLOS) or Ricean (LOS).
- Example: Narrowband voice channels (GSM 200 kHz bandwidth in urban where Bc > 200 kHz).

##### 2b. Frequency-Selective Fading (Wideband Fading)

- **Condition:** `Bs >> Bc` OR `σ_τ >> Ts` (delay spread >> symbol period)
- Channel **bandwidth < signal bandwidth** — different spectral components fade differently.
- **ISI is present** — multipath delay spread causes echoes to spill into adjacent symbols.
- Channel modeled as **multi-tap FIR filter**: `r(t) = Σ hₙ(t)·s(t−τₙ) + n(t)`
- Example: 4G LTE with 10 MHz bandwidth in urban environments where Bc ~ 100 kHz.

---

#### Dimension 2 — Based on DOPPLER SPREAD (Channel Time Variation vs Symbol Rate)

This determines whether the channel changes significantly during one symbol.

##### 2c. Fast Fading

- **Condition:** `Tc << Ts` OR `BD >> Bs` (Doppler spread >> signal bandwidth)
- Channel coherence time `Tc` is **shorter than symbol period** `Ts`.
- Channel **changes significantly within one symbol duration**.
- Causes **distortion** — channel variation during symbol → inter-carrier interference in OFDM.
- Occurs in **high-speed vehicles** (cars at 100+ km/h, high-frequency carriers).
- Hard to estimate and track channel — fast variations outpace estimation.
- Solution: Faster pilot insertion, shorter symbols, Doppler compensation.

##### 2d. Slow Fading

- **Condition:** `Tc >> Ts` OR `BD << Bs` (Doppler spread << signal bandwidth)
- Channel coherence time is **much longer than symbol period**.
- Channel changes slowly — **many symbols experience approximately the same fading**.
- Easier to track with pilot-based channel estimation.
- Occurs in **pedestrian speed or stationary** environments.
- Example: Indoor Wi-Fi users, slow-walking pedestrians.

---

### Summary Classification Table

| Classification | Criterion | Effect | Example |
|---|---|---|---|
| **Path Loss** | Distance d | Slow power decrease | d increases → received power drops |
| **Shadowing** | Large obstacles | Slow random variation (~6-12 dB std dev) | Building blocks LOS |
| **Flat Fading** | Bs << Bc, σ_τ << Ts | Entire signal fades uniformly | GSM voice |
| **Frequency-Selective** | Bs >> Bc, σ_τ >> Ts | ISI; different freqs fade differently | 4G LTE |
| **Fast Fading** | Tc << Ts, BD > Bs | Channel changes within a symbol | High-speed car |
| **Slow Fading** | Tc >> Ts, BD < Bs | Channel stable over many symbols | Pedestrian |

---

### Key Parameters Summary

| Parameter | Symbol | Formula | Meaning |
|---|---|---|---|
| **RMS Delay Spread** | σ_τ | Second central moment of PDP | Spread of multipath delays |
| **Coherence Bandwidth** | Bc | ≈ 1/(5σ_τ) | BW over which channel is flat |
| **Doppler Spread** | BD | fD = v·fc/c | Frequency spread due to motion |
| **Coherence Time** | Tc | ≈ 0.423/fD_max | Duration over which channel is stable |
| **Symbol Period** | Ts | 1/Rs | Duration of one data symbol |
| **Signal Bandwidth** | Bs | ≈ Rs | Bandwidth occupied by signal |

---

## Diagram

```
COMPLETE FADING TYPES — ILLUSTRATED

LARGE-SCALE (slow, location-dependent):

   Power (dBm)
     │
   -60│ ·  ·
     │   ·   ·
   -80│       ·  ·
     │           ·   Path loss + shadowing
  -100│               ·  ·  ·
     └──────────────────────→ Distance (km)

SMALL-SCALE (fast, local):

   Power (dBm)
     │   ___
     │  /   \        ___
   -60│ /     \      /   \      /\
     │/       \    /     \    /  \
   -80│         \__/       \__/    \__
     │
     └──────────────────────→ Distance (wavelengths)
     ← rapid oscillations within meters →

FLAT vs FREQUENCY-SELECTIVE:

Flat Fading:                   Frequency-Selective:
  │H(f)│                          │H(f)│
   ────────── (flat)                /\  \/\  (varies with f)
    ↕ amplitude                    /  \/  \
    varies but                    /        \
    all freqs same
    ↕

FAST vs SLOW FADING (Time domain):

Fast Fading:                   Slow Fading:
  h(t)                           h(t)
   /\/\/\/\/\/\/\/\/               ─────/\────────────
  Rapid changes within            Channel stable for
  one symbol period               many symbol periods
```

*Figure: Complete Fading Classification — Large-Scale and Small-Scale*

---

## Example

**Real-World Example (Urban 4G LTE):**

- **Path Loss + Shadowing:** User 500m from base station, behind a building — received power = path loss + 8 dB shadow loss.
- **Frequency-Selective Fading:** LTE uses 10 MHz BW; urban Bc ≈ 100 kHz → signal experiences frequency-selective fading → ISI → solved by OFDM.
- **Slow Fading:** User walking at 3 km/h → Doppler = 3×1800M/3×10⁸ = 6 Hz → Tc ≈ 70 ms >> LTE symbol = 71 µs → slow fading.
- **Fast Fading (car on highway):** Speed = 120 km/h → fD = 200 Hz → Tc = 2 ms — could approach fast fading for some OFDM subcarriers.

---

## Conclusion

Fading is a **multi-dimensional phenomenon** in wireless channels. It operates at different spatial scales (large-scale path loss and shadowing) and manifests differently depending on **signal bandwidth vs coherence bandwidth** (flat vs frequency-selective) and **symbol rate vs channel variation rate** (fast vs slow fading). Understanding this classification is fundamental to designing the correct **modulation, coding, diversity, and equalization** strategies for any wireless system.

---

# UNIT REVISION TABLE

| Topic | Key Points |
|---|---|
| **Rayleigh PDF** | f(r)=(r/σ²)·exp(−r²/2σ²) · Mean=σ√(π/2) · Var=σ²(2−π/2) · NLOS · K=0 |
| **Ricean Model** | LOS component present · K-factor=A²/2σ² · I₀ Bessel function · K=0→Rayleigh · K→∞→AWGN |
| **Non-Coherent FSK** | Two parallel BPFs (f₁, f₀) · Envelope detectors · Comparator · No phase reference · 3dB penalty |
| **Multipath** | Reflection · Diffraction · Scattering · h(τ)=Σaₙδ(τ−τₙ) · ISI when τmax>Ts |
| **ISI** | Delayed echoes corrupt next symbol · Solved by OFDM/equalizer/cyclic prefix/Rake |
| **Narrowband** | Bs<<Bc · Flat fading · No ISI · Models: AWGN, Rayleigh flat |
| **Wideband** | Bs>>Bc · Frequency selective · ISI · Models: Saleh-Valenzuela, COST207 |
| **Large-Scale Fading** | Path loss (distance) · Shadowing (log-normal, σ=6-12 dB) · Slow variation |
| **Small-Scale Fading** | Time spreading: Flat/Freq-selective · Doppler: Fast/Slow |
| **Flat Fading** | σ_τ<<Ts · Bs<<Bc · Uniform fading · Single tap · No ISI |
| **Frequency Selective** | σ_τ>>Ts · Bs>>Bc · ISI · Multi-tap · OFDM needed |
| **Fast Fading** | Tc<<Ts · BD>Bs · High mobility · Channel changes within symbol |
| **Slow Fading** | Tc>>Ts · BD<Bs · Pedestrian speed · Channel stable across symbols |

---

# One-Day Exam Revision Notes

### Rayleigh — Must-Know Formulas
```
f(r) = (r/σ²)·exp(−r²/2σ²)        PDF
P(r≤R) = 1 − exp(−R²/2σ²)          CDF (outage probability)
E[r]   = σ√(π/2)  ≈ 1.253σ         Mean
E[r²]  = 2σ²                        Mean power
Var(r) = σ²(2 − π/2) ≈ 0.429σ²     Variance
```

### Ricean — K-Factor Memory
```
K = A²/(2σ²)     (LOS power / scattered power)
K = 0   →  Rayleigh (no LOS)
K → ∞   →  AWGN (pure LOS, no fading)
PDF has I₀(Bessel) term — signature of Ricean
```

### Non-Coherent FSK — Block Sequence
```
r(t) → BPF(f₁) → Envelope Detector → Sample → E₁ ─┐
                                                     ├→ Comparator → bit
     → BPF(f₀) → Envelope Detector → Sample → E₀ ─┘
E₁>E₀: bit '1', E₀>E₁: bit '0'
BER = (1/2)·exp(−Eb/2N₀)   [3 dB worse than coherent]
```

### ISI Condition — One Line
```
τmax > Ts  →  ISI!    (delay spread exceeds symbol period)
Solution: OFDM (cyclic prefix makes τmax < CP length)
```

### Fading Classification — Quick Tree
```
Fading → Large Scale: Path Loss + Shadowing
       → Small Scale → Time Spread: Flat (Bs<Bc) / Freq-Selective (Bs>Bc)
                    → Doppler:     Slow (Tc>Ts) / Fast (Tc<Ts)
```

### Channel Models — 2-Second Memory
```
Narrowband: AWGN (no fading) + Rayleigh (NLOS flat)
Wideband:   Saleh-Valenzuela (indoor clusters) + COST207 (outdoor: RA/TU/BU/HT)
```

---

# Frequently Repeated SPPU Questions

| Question | Frequency | Marks |
|---|---|---|
| Rayleigh distribution — PDF, Mean, Variance | ★★★★★ Very High (MJ23, MJ24, ND24, MJ25) | 7–9 marks |
| Ricean fading + comparison with Rayleigh | ★★★★★ Very High (ND25, ND23, MJ25, MJ24, ND24) | 6–7 marks |
| Non-coherent FSK detection with diagram | ★★★★★ Very High (ND24, MJ24, MJ23, ND23) | 7–9 marks |
| Multipath propagation + ISI | ★★★★ High (ND25, ND24, MJ24, MJ23) | 7–9 marks |
| Wideband vs Narrowband channels + models | ★★★★ High (MJ25, MJ23, ND23, MJ24) | 6–7 marks |
| Fading types — classification and explanation | ★★★ Medium (ND25, MJ25, ND23) | 7 marks |

---

# Last Minute Keywords

**Rayleigh:** NLOS · No LOS · Gaussian I and Q · σ² variance · PDF = (r/σ²)exp(−r²/2σ²) · Mean = σ√(π/2) · Variance = σ²(2−π/2) · CDF = 1−exp(−R²/2σ²) · Mode = σ

**Ricean:** LOS component · K-factor · A = LOS amplitude · Bessel function I₀ · K=0→Rayleigh · Suburban · Indoor · Satellite · Less severe fading

**Non-Coherent FSK:** No phase reference · BPF · Envelope detector · Comparator · Two branches (f₁, f₀) · E₁ vs E₀ · BER = (1/2)exp(−Eb/2N₀) · 3 dB penalty · Bluetooth GFSK

**Multipath:** Reflection · Diffraction · Scattering · Delay spread · τmax · Power Delay Profile · h(τ) · ISI · Rayleigh fading · Coherence bandwidth

**ISI:** τmax > Ts · Delayed echoes · Error floor · Equalizer · OFDM · Cyclic prefix · Rake receiver · MLSE

**Narrowband:** Bs<<Bc · Flat fading · No ISI · Single tap · AWGN model · Rayleigh flat fading model

**Wideband:** Bs>>Bc · Frequency-selective · ISI · Multi-tap · Saleh-Valenzuela (clusters, indoor, UWB) · COST207 (RA/TU/BU/HT, outdoor, GSM/3G)

**Fading Types:** Large-scale (path loss + shadowing) · Small-scale (flat/freq-selective + fast/slow) · Coherence bandwidth Bc=1/(5σ_τ) · Coherence time Tc=0.423/fD · Doppler spread BD

---

*End of Unit Notes — Wireless Channel Modeling, Fading & Detection*
*Pattern: SPPU 2019 & 2024 Compatible*
*Covers: ND25 · MJ25 · ND24 · MJ24 · MJ23 · ND23*
