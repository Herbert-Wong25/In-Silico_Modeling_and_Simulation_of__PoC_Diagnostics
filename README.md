# Modeling and Simulation of Automated PoC Diagnostics

### **Awarded Distinction | MRes in Bioengineering, Imperial College London (2020)**

This repository showcases the computational research and design optimization for my Master's thesis. The project focused on the **simulation-guided development** of an automated, nanocatalyst-amplified Lateral Flow Immunoassay (LFIA). By integrating fluid dynamics and molecular binding kinetics, I developed a predictive model to automate complex, multi-step diagnostic assays into a single, user-friendly Point-of-Care (PoC) device.

## 🔬 Scientific Context

Traditional Lateral Flow Assays (like rapid COVID tests) are fast but often lack the sensitivity required for early-stage disease detection. **Nanocatalysts (e.g., Platinum Nanoparticles - PtNPs)** can amplify signals to ELISA-like sensitivity, but they require precise, multi-step "wash and develop" sequences.

This project utilized **In Silico Modeling** to:

1. **Automate Reagent Delivery:** Using paper geometry and fluidic physics to time the arrival of amplification reagents without user intervention.
2. **Optimize Molecular Capture:** Using kinetic modeling to compare the performance of Nanobodies (Nb) vs. Monoclonal Antibodies (mAb) under flow.

![Open View of Assembled LFA Device](design_blueprints/LFA_Assembled_View.png)
*Figure 1: 3D assembly of the automated LFIA device designed in SolidWorks, featuring independent channels for sample, wash buffer, and amplification reagents.*

## 🛠 Tech Stack & Dependencies

* **Computational Modeling:** Python (NumPy, SciPy, Pandas)
* **CAD/Design:** SolidWorks (Device architecture)
* **Data Analysis:** Matplotlib, Seaborn
* **Core Concepts:** Washburn’s Law, Langmuir Kinetics, Mass Transport, Microfluidics

---

## 🚀 The Simulation Pipeline

### Part 1: Fluid Dynamics & Device Dimensioning

To automate the assay, I modeled the capillary flow (wicking) through nitrocellulose membranes.

* **Notebook:** `01_Fluid_Dynamics_and_LFA_Design_Optimization.ipynb`
* **Innovation:** Implemented **linear interpolation** to estimate fluidic parameters (viscosity, surface tension) for non-standard channel widths (3mm, 4mm), enabling the design of custom "Design 2" geometry.
* **Result:** Determined exact channel lengths ($L_1, L_2, L_3$) to ensure reagents arrive at the test line at specific 2-minute and 5-minute intervals.

### Part 2: Multi-Phase Binding Kinetics

I modeled the chemical interaction at the test line to predict the Limit of Detection (LoD).

* **Notebook:** `02_Binding_Kinetics_Modeling.ipynb`
* **3-Phase Model:** Simulated the arrival (Phase 1), binding (Phase 2), and wash/purification (Phase 3) of the nanoparticle-target complex.
* **Finding:** Validated that **Nanobody 59H10** achieved superior capture efficiency in short time-frames compared to standard mAbs, making it the ideal candidate for rapid PoC detection.

---

## 📊 Key Quantitative Metrics

The project implemented the following mathematical models from the thesis to bridge the gap between fluidic delivery and molecular capture:

### 1. Fluidic Flow Rate Modeling

The capillary pressure ($P_c$) and travel velocity ($V$) were optimized to establish the automated timeline:

**Eq.1: Simplified Capillary Pressure**


$$P_c = \gamma \left( \frac{2 \cos(\theta)}{h} + \frac{2 \cos(\theta)}{w} \right)$$

**Eq.2: Travel Velocity**


$$V = k \frac{2 \cos(\theta)(h+w)}{6LC}$$

**Eq.3: Linear Interpolation for Parameter Estimation**


$$\frac{k - k_1}{w - w_1} = \frac{k_i - k_1}{w_i - w_1}$$

### 2. Binding Kinetics Modeling

The molecular capture and affinity were quantified using the law of mass action and equilibrium constants:

**Eq.4: Law of Mass Action**


$$[Ag] + [mAb] \xrightleftharpoons[k_d]{k_a} [Ag\text{-}mAb]$$

**Eq.5: Dissociation Constant ($K_D$)**


$$K_{eq} = \frac{k_a}{k_d} = \frac{[Ag\text{-}mAb]}{[Ag][mAb]} \quad ; \quad K_D = \frac{1}{K_{eq}}$$

---
## 📈 Results & Conclusion

This *in silico* research successfully demonstrated the feasibility of achieving a fully automated, nanocatalyst-amplified LFIA, leading to a **Distinction** award at **Imperial College London**.

* **Simulation-Guided Design Success:** The 1D flow model effectively optimized the channel dimensions for "Design 2," identifying the specific lengths required to synchronize a multi-step assay into a seamless 10-minute automated window.
* **Dimensionally Defined Design:** Numerical evidence confirmed that a **4 mm wide device** with channel lengths of **$L_1=35$ mm**, **$L_2=64$ mm**, and **$L_3=90$ mm** theoretically achieves full automation of sequential flow at precisely timed intervals.

![Dimensioned Schematic of LFIA Design](design_blueprints/Dimensioned_Schematic.png)
*Figure 2: Optimized device schematic showing the final calculated dimensions derived from Washburn and Darcy flow simulations.*

* **Superiority of Nanobodies (Nb):** Kinetic simulations identified **Nanobody 59H10** as having the highest relative affinity towards p24, outperforming standard mAbs during the critical Phase 3 wash period.
* **Final Impact:** The project proved that **In Silico Modeling** can accurately predict PoC device performance, significantly reducing the cost and time of physical prototyping in diagnostic R&D.

---


## 📂 Project Structure

```text
/Automated_LFIA_Simulation
  ├── /notebooks
  │     ├── 01_Fluid_Dynamics_and_LFA_Design_Optimization.ipynb
  │     └── 02_Binding_Kinetics_Modeling.ipynb
  ├── /design_blueprints
  │     ├── LFA_Assembled_View.png          (SolidWorks Render)
  │     └── Dimensioned_Schematic.png       (Simulation Results)
  ├── /thesis_assets
  │     └── MRes_Imperial_Thesis.pdf
  ├── requirements.txt                      (Python Environment)
  └── README.md

```

---

## 🏆 Key Achievements & Impact

* **Distinction Awarded:** The thesis was recognized for its high technical rigor and potential for real-world diagnostic impact.
* **Validation of Automation:** Proved *in silico* that a multi-stage "wash-and-amplify" assay can be reduced to a single-step user action.
* **Optimized Sensitivity:** Identified specific nanobody-nanoparticle pairings that increase signal output by >30% within the target 10-minute test window.

---

## ✉️ Contact

For inquiries regarding In Silico Modeling or Point-of-Care device engineering, contact **Herbert Siu-Ho Wong** at [herbert.wong150@gmail.com].

