# Medical Statistics Playground 🧪📊

A set of small, self-contained **Evidence-Based Medicine (EBM)** and **medical statistics** playgrounds.

Each file `EBMPG1.html` … `EBMPG8.html` is a **single-page app** (HTML + CSS + JS in one file) that runs **entirely offline** in any modern browser.  
They’re designed for **live teaching**: move sliders, change numbers, and instantly show how the stats behave.

---

## 🚏 Overview of Playgrounds

> All files are named `EBMPG#.html` (from 0 to 8).  
> Open them directly in your browser. The title inside each file tells you what it does.


### EBMPG1.html – Study Design & Evidence Explorer

Explore the **hierarchy of evidence** and study designs:

- Compare:
  - RCTs
  - Cohort studies
  - Case–control studies
  - Cross-sectional studies
- Show how design affects:
  - **Internal validity**
  - **Susceptibility to bias**
  - **Typical effect measures** (risk ratio, odds ratio, etc.)
- Use presets to illustrate:
  - When a cohort is reasonable vs when an RCT is needed
  - Why case–control studies can’t give you risk directly

Great for the “How strong is this evidence?” part of EBM.

---

### EBMPG2.html – Effect Sizes & Risk Measures

A playground for **risk and effect size interpretation**:

- Enter control and treatment event rates.
- See:
  - **Risk difference (absolute risk reduction)**  
  - **Relative risk (RR)**  
  - **Odds ratio (OR)**  
  - **Relative risk reduction (RRR)**  
  - **Number needed to treat (NNT)** / **harm (NNH)** when appropriate
- Demonstrate:
  - How RR and OR diverge when events are common.
  - How the same RR can correspond to very different **absolute** risk reductions depending on baseline risk.
  - Why clinicians often care more about **absolute** measures (ARR, NNT) than purely relative ones.

---

### EBMPG3.html – Diagnostic Test & Bayes

Diagnostic reasoning + Bayesian updating in one place:

- Build a **2×2 table**:
  - Disease / no disease × Test positive / negative
- Live outputs:
  - **Sensitivity**, **specificity**
  - **PPV**, **NPV**
  - **Likelihood ratios** (LR+ and LR−)
- Bayes part:
  - Set **pre-test probability**
  - Apply LRs to get **post-test probability**
- Teaching points:
  - Why a “good test” in a low-prevalence population still yields many false positives.
  - How pre-test probability (clinical judgment) and test characteristics combine in practice.

---

### EBMPG4.html – P-values, Confidence Intervals & Power

A simulation lab for inferential statistics:

- Choose:
  - **True effect size**
  - **Standard deviation / variability**
  - **Sample size (n)**
  - **Significance level (α)**
- Run repeated “trials” to see:
  - The **distribution of p-values** for the same true effect.
  - How often a study is “significant” → empirical **power**.
  - The width and location of **95% confidence intervals**.
- Use it to show:
  - “Non-significant” does **not** mean “no effect”.
  - Larger n → narrower CIs, more stable p-values.
  - Power is the probability of detecting a real effect, not a property of the data you already collected.

---

### EBMPG5.html – Confounding, Bias & Adjustment

Explore how confounding and adjustment change effect estimates:

- Conceptual setup:
  - A treatment/exposure **A**
  - An outcome **Y**
  - A confounder **C** affecting both A and Y
- Show:
  - **Crude effect** (A → Y) when ignoring C.
  - **Adjusted effect** after accounting for C (e.g. stratification or regression-style logic).
- Demonstrate:
  - How confounding can **inflate**, **attenuate**, or even **reverse** an apparent effect.
  - The difference between:
    - **Confounding** (third variable distorts an association)
    - **Selection bias** (distortion by who enters the sample)
- Great for the “association vs causation” and “why adjustment matters” discussion.

---

### EBMPG6.html – Meta-analysis & Heterogeneity Lab

A tiny **meta-analysis** and **heterogeneity** visualizer:

- Enter (or use presets):
  - Study-level estimates (e.g. log RR / log OR)
  - Standard errors or variances
- Outputs:
  - **Fixed-effect** pooled estimate
  - **Random-effects** pooled estimate (e.g. DerSimonian–Laird)
  - Heterogeneity statistics: **Q**, **I²**, **τ²**
- Interactive **forest plot**:
  - Squares (study estimates) sized by weight
  - Diamond for the pooled effect
  - Toggle fixed vs random to see how weights change
  - Option to omit individual studies and see the impact
- Teaching points:
  - What heterogeneity really means.
  - Why a pooled effect can be misleading when studies strongly disagree.

---

### EBMPG7.html – Risk of Bias & GRADE Playground

Two connected modules:

1. **Risk-of-Bias (RoB 2 style) traffic light**

   - Domains:
     - Randomization process  
     - Deviations from intended interventions  
     - Missing outcome data  
     - Measurement of outcome  
     - Selection of reported result  
   - Per-domain judgment: **Low / Some concerns / High**
   - Overall rule:
     - Any **High** → overall **High risk of bias**
     - Else any **Some concerns** → overall **Some concerns**
     - Else → **Low risk of bias**
   - Includes presets like:
     - “Perfect RCT”
     - “Poor concealment”
     - “High loss to follow-up”
     - “Messy open-label trial”

2. **GRADE certainty of evidence**

   - Starting point:
     - **High** (for randomized trials)  
     - **Low** (for observational studies)
   - For each GRADE domain, choose:
     - 0 = no serious concerns  
     - −1 = serious  
     - −2 = very serious  
   - The app computes:
     - Total downgrades
     - Final certainty level: **High / Moderate / Low / Very low**
     - A short explanatory narrative (which domains caused the downgrades).

Use this to connect **methodological quality** → **how much we trust the effect size**.

---

### EBMPG8.html – Survival & Correlation Playground

Two advanced topics combined:

1. **Survival curves & hazard ratios**

   - Simulate a 2-arm trial:
     - **True hazard ratio** (treatment vs control)
     - **Sample size per arm**
     - Approx **censoring percentage**
     - **Max follow-up** time
     - **Baseline hazard / event rate** in control
   - Outputs:
     - Kaplan–Meier curves for each arm
     - Approximate **hazard ratio** from observed data
     - Events vs censored counts
     - Median survival times (if reached)
   - Teaching points:
     - Why survival analysis is needed when follow-up times differ.
     - How censoring and small N affect KM curves and HR estimates.

2. **Correlation ≠ causation sandbox**

   - Generate variables:
     - Hidden common cause **U**
     - X = f(U) + noise
     - Y = g(U) + optional direct **X → Y** effect + noise
   - Controls:
     - Strength of the **common cause**
     - **Noise** level
     - Size of the **direct effect X → Y**
     - **Sample size**
   - Outputs:
     - Scatter plot of X vs Y
     - **Pearson r**, **R²**, and regression slope
   - Show:
     - That strong correlation can arise purely from a **shared cause**.
     - Why correlation alone doesn’t settle causality.

---

## 🚀 Getting started

1. **Clone or download** the repo:

   ```bash
   git clone https://github.com/<your-username>/Medical-Statistics-Playground.git
   cd Medical-Statistics-Playground
   
   
2. **Open any playground:**

  - Double-click EBMPG1.html (or any other file)

  - Or right-click → “Open with…” → choose your browser

3. **You’re done.**
  - No dependencies, no build step, no server – just open in browser and play.

***OR***
**You can open GitHub Pages for this repo from here:**
  - https://yashar-jb.github.io/Medical-Statistics-Playground/index.html

