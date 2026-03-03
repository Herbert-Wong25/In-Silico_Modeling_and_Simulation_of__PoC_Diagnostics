# Modeling and Simulation of Automated PoC Diagnostics

### **🌟 Awarded Distinction | MRes in Bioengineering, Imperial College London**

This repository showcases the computational research and design optimization for my Master's thesis. The project focused on the **simulation-guided development** of an automated, nanocatalyst-amplified Lateral Flow Immunoassay (LFIA). By integrating fluid dynamics and molecular binding kinetics, I developed a predictive model to automate complex, multi-step diagnostic assays into a single, user-friendly Point-of-Care (PoC) device.

## 🔬 Scientific Context

Traditional Lateral Flow Assays (like rapid COVID tests) are fast but often lack the sensitivity required for early-stage disease detection. **Nanocatalysts (e.g., Platinum Nanoparticles - PtNPs)** can amplify signals to ELISA-like sensitivity, but they require precise, multi-step "wash and develop" sequences.

This project utilized **In Silico Modeling** to:

1. **Automate Reagent Delivery:** Using paper geometry and fluidic physics to time the arrival of amplification reagents without user intervention.
2. **Optimize Molecular Capture:** Using kinetic modeling to compare the performance of Nanobodies (Nb) vs. Monoclonal Antibodies (mAb) under flow.

![Open View of Assembled LFA Device](design_blueprints/LFA_Assembled_View.png)
*Figure 1: 3D assembly of the automated LFIA device designed in SolidWorks, featuring independent channels for sample, wash buffer, and amplification reagents.*

## 🛠 Tech Stack & Dependencies

* **Computational Modeling:** Python (NumPy, Matplotlib)
* **CAD/Design:** SolidWorks (Device architecture)
* **Core Concepts:** Washburn's Law, Langmuir Kinetics, Mass Transport, Microfluidics

---

## 🚀 The Simulation Pipeline

### Part 1: Fluid Dynamics & Device Dimensioning

To automate the assay, I modeled the capillary flow (wicking) through nitrocellulose membranes.

* **Notebook:** `01_Fluid_Dynamics_and_LFA_Design_Optimization.ipynb`
* **Innovation:** Implemented **linear interpolation** to estimate fluidic parameters for non-standard channel widths (3 mm, 4 mm), enabling the design of "Design 2" geometry.
* **Result:** Determined exact channel lengths ($L_1$, $L_2$, $L_3$) to ensure each reagent reaches the test line at precisely the **2-minute** (AuNP), **5-minute** (PBS), and **10-minute** (DAB) marks.

### Part 2: Multi-Phase Binding Kinetics

I modeled the molecular interaction at the test line to predict capture efficiency.

* **Notebook:** `02_Binding_Kinetics_Modeling.ipynb`
* **3-Phase Model:** Simulated the arrival (Phase 1), binding at the test line (Phase 2), and PBS wash/dissociation (Phase 3) of the nanoparticle-target complex.
* **Finding:** Validated that **Nanobody 59H10** achieved superior capture efficiency and wash retention compared to standard mAbs, making it the optimal candidate for PtNC conjugation.

---

## 📊 Key Quantitative Metrics

### 1. Fluidic Flow Rate Modeling

**Eq.1: Simplified Capillary Pressure**

$$P_c = \gamma \left( \frac{2 \cos(\theta)}{h} + \frac{2 \cos(\theta)}{w} \right)$$

**Eq.2: Travel Velocity**

$$V = k \frac{2 \cos(\theta)(h+w)}{6LC}$$

**Eq.3: Linear Interpolation for Parameter Estimation**

$$\frac{k - k_1}{w - w_1} = \frac{k_i - k_1}{w_i - w_1}$$

### 2. Binding Kinetics Modeling

**Eq.4: Law of Mass Action**

$$[Ag] + [Ab] \xrightleftharpoons[k_d]{k_a} [Ag\text{-}Ab]$$

**Eq.5: Equilibrium Dissociation Constant**

$$K_D = \frac{k_d}{k_a}$$

---

## 📈 Results & Conclusion

This *in silico* research successfully demonstrated the feasibility of achieving a fully automated, nanocatalyst-amplified LFIA, leading to a **Distinction** award at **Imperial College London**.

* **Simulation-Guided Design:** The 1D flow model optimized the channel dimensions for "Design 2," confirming that a **4 mm wide device** with channel lengths of $L_1 = 35$ mm, $L_2 = 64$ mm, and $L_3 = 90$ mm achieves full automation of sequential reagent delivery within a 10-minute window.

![Dimensioned Schematic of LFIA Design](design_blueprints/Dimensioned_Schematic.png)
*Figure 2: Optimized device schematic showing the final calculated dimensions derived from Washburn and Darcy flow simulations.*

* **Superiority of Nanobodies:** Kinetic simulations identified **Nanobody 59H10** (Gray et al., 2017) as having the highest affinity toward HIV p24, with the greatest signal retention after the Phase 3 wash — outperforming both mAbs and the competing nanobody 37E7.
* **Impact:** The project proved that *in silico* modelling can accurately predict PoC device performance, significantly reducing the cost and time of physical prototyping in diagnostic R&D.

---

## 📂 Project Structure

```text
/In-Silico_Modeling_and_Simulation_of_PoC_Diagnostics
  ├── /notebooks
  │     ├── 01_Fluid_Dynamics_and_LFA_Design_Optimization.ipynb
  │     └── 02_Binding_Kinetics_Modeling.ipynb
  ├── /design_blueprints
  │     ├── LFA_Assembled_View.png          (SolidWorks Render)
  │     └── Dimensioned_Schematic.png       (Simulation Results)
  ├── /thesis_assets
  │     └── MRes_Imperial_Thesis.pdf
  ├── requirements.txt
  └── README.md
```

---

## 🏆 Key Achievements

* **Distinction Awarded:** Recognised for high technical rigor and potential for real-world diagnostic impact.
* **Validation of Automation:** Proved *in silico* that a multi-stage "wash-and-amplify" assay can be reduced to a single-step user action.
* **Material Selection:** Identified Nanobody 59H10 as the optimal binder for PtNC conjugation based on kinetic modelling of all four candidate Nb/mAb reagents.

---

## ✉️ Contact

For inquiries regarding In Silico Modeling or Point-of-Care device engineering, contact **(Herbert) Siu-Ho Wong** at [herbert.wong150@gmail.com].
