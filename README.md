# Inference & Information: Foundations, Machine Learning & Systems Discovery
### *The MacKay-McElreath Synthesis: From Surprise & Bayes' Rule to Information Geometry & Active Learning*

Welcome to **Inference & Information**! This curriculum unifies **Bayesian Inference** and **Information Theory** into a single, cohesive, end-to-end framework. 

Rather than teaching Bayesian statistics in isolation (posteriors, priors, and MCMC) and Information Theory in isolation (bits, entropy, and channel codes), this course reveals how they are two sides of the same coin:
* **Bayesian Inference** provides the *calculus of belief updating*.
* **Information Theory** provides the *currency of uncertainty and the fundamental physical limits of learning*.

---

## 🎯 The Pedagogical Through-Line: The Flaky Test & Production Systems Challenge

Abstract probability often feels detached from physical reality. To keep our feet planted firmly on the ground, this entire curriculum uses a concrete, multi-billion-dollar engineering challenge as its primary case study: **The Flaky Test Problem in Large-Scale Distributed CI/CD Systems**.

A test that fails $100\%$ of the time is easy: one run delivers $100\%$ certainty. But a **flaky test** is a stochastic particle in a noisy machine. It fails intermittently ($P(\text{Fail}) = \theta \in (0, 1)$) due to race conditions, thread starvation, network jitter, and memory pressure. 

Every statistical concept in this course answers an immediate operational question:
* *How many bits of uncertainty remain about a test's stability?* (**Shannon Entropy**)
* *How much did a batch of 10 test runs update our beliefs?* (**Beta-Binomial Conjugacy & KL Divergence**)
* *How do we set a fair prior on failure rates across a 50,000-test monorepo?* (**The MaxEnt Principle**)
* *Did two tests fail due to the same database timeout, or independent bugs?* (**Mutual Information & Venn Geometry**)
* *Should we merge this PR or spend cloud compute re-running the test?* (**Bayesian Decision Theory & Wald SPRT**)
* *Which commit broke the build across 1,000 commits with the minimum number of expensive test re-runs?* (**Lindley Expected Information Gain & Active Learning**)

*(When classical physical systems—like fair dice, ideal gases, or genomic DNA—provide a cleaner intuitive starting point, we introduce them as the foundational metaphor before deploying the machinery to production software systems).*

---

## 🚗 Twin Companion Architecture

The curriculum is organized into **two synchronized 1-to-1 parallel tracks**:

* 📖 **[Conceptual Track (`conceptual/`)](conceptual/)**: A pure reading edition focusing on mental models, mathematical derivations, and physical intuition.
* 🐍 **[Python Laboratory (`python/`)](python/)**: A hands-on computational lab manual implementing every algorithm, simulation, and theorem from scratch using `numpy`, `scipy`, and `matplotlib`.

---

## 📚 Master Curriculum Syllabus (`00`–`12`)

| Ch | Conceptual Track | Python Lab | Core Focus & Integrated Concepts |
| :---: | :--- | :--- | :--- |
| **00** | **[Ch 00: The Physics of Belief](conceptual/00_the_physics_of_belief.ipynb)** | **[Ch 00 (Python)](python/00_the_physics_of_belief.ipynb)** | What is Knowledge? Determinism vs. Flakiness, The 20 Questions Game, Why Information is Logarithmic ($I = -\log_2 p$). |
| **01** | **[Ch 01: Quantifying Uncertainty](conceptual/01_quantifying_uncertainty_entropy_and_bayes.ipynb)** | **[Ch 01 (Python)](python/01_quantifying_uncertainty_entropy_and_bayes.ipynb)** | Shannon Entropy $H(X)$ meets the Beta-Binomial Update. Measuring the exact bits of uncertainty resolved by test runs. |
| **02** | **[Ch 02: The Price of Optimism](conceptual/02_relative_entropy_and_prior_penalties.ipynb)** | **[Ch 02 (Python)](python/02_relative_entropy_and_prior_penalties.ipynb)** | Relative Entropy (Kullback-Leibler Divergence $D_{\text{KL}}$) as the penalty of believing a flaky test is solid. Gibbs' Inequality & Kraft codes. |
| **03** | **[Ch 03: Where Fleet Priors Come From](conceptual/03_maximum_entropy_priors.ipynb)** | **[Ch 03 (Python)](python/03_maximum_entropy_priors.ipynb)** | E.T. Jaynes' Principle of Maximum Entropy (MaxEnt). Deriving Exponential, Gaussian, and Uniform priors from physical moment constraints. |
| **04** | **[Ch 04: Shared Outages & Venn Geometry](conceptual/04_mutual_information_and_venn_geometry.ipynb)** | **[Ch 04 (Python)](python/04_mutual_information_and_venn_geometry.ipynb)** | Joint Distributions $P(X, Y)$, Mutual Information $I(X; Y)$, The Information Venn Diagram, Confounders vs. Colliders (The Reversal Paradox). |
| **05** | **[Ch 05: The Geometry of Inference](conceptual/05_curvature_laplace_and_fisher_information.ipynb)** | **[Ch 05 (Python)](python/05_curvature_laplace_and_fisher_information.ipynb)** | The Laplace Approximation, The Hessian Curvature, and the Fisher Information Matrix $\mathcal{I}(\theta)$. The Riemannian metric of probability. |
| **06** | **[Ch 06: The Engine of Computation: MCMC](conceptual/06_mcmc_mechanics_and_entropy.ipynb)** | **[Ch 06 (Python)](python/06_mcmc_mechanics_and_entropy.ipynb)** | Markov Chains, Detailed Balance, Metropolis-Hastings from scratch, and why maximum entropy proposals explore parameter spaces fastest. |
| **07** | **[Ch 07: Compression & Hierarchy](conceptual/07_compression_and_hierarchy_information_bottleneck.ipynb)** | **[Ch 07 (Python)](python/07_compression_and_hierarchy_information_bottleneck.ipynb)** | Hierarchical Bayesian models & James-Stein shrinkage meet Tishby's Information Bottleneck. Shrinkage as lossy compression of group noise. |
| **08** | **[Ch 08: Model Comparison as Code Efficiency](conceptual/08_model_comparison_as_code_efficiency.ipynb)** | **[Ch 08 (Python)](python/08_model_comparison_as_code_efficiency.ipynb)** | Out-of-Sample Predictive Density, Cross-Entropy Loss, and why WAIC / PSIS-LOO measure expected KL divergence from ground-truth nature. |
| **09** | **[Ch 09: To Merge or Re-Run?](conceptual/09_bayesian_decision_theory_and_wald_sprt.ipynb)** | **[Ch 09 (Python)](python/09_bayesian_decision_theory_and_wald_sprt.ipynb)** | Bayesian Decision Theory (Losses & Utility) meets Shannon Channel Capacity and Abraham Wald's Sequential Probability Ratio Test (SPRT). |
| **10** | **[Ch 10: Active Learning & Culprit Bisection](conceptual/10_active_learning_and_culprit_bisection.ipynb)** | **[Ch 10 (Python)](python/10_active_learning_and_culprit_bisection.ipynb)** | Dennis Lindley's Expected Information Gain (EIG), Bayesian culprit posterior updating under flakiness, Horstein probabilistic bisection, and BALD active learning. |
| **11** | **[Ch 11: Production Capstone](conceptual/11_production_capstone_autonomous_triage_bot.ipynb)** | **[Ch 11 (Python)](python/11_production_capstone_autonomous_triage_bot.ipynb)** | End-to-end autonomous CI triage bot: non-stationary tracking with exponential forgetting ($\gamma$), cost-optimal quarantine entry, and posterior predictive streak exit gates. |
| **12** | **[Ch 12: The Master Rosetta Stone](conceptual/12_master_rosetta_stone_and_notation_guide.ipynb)** | **[Ch 12 (Python)](python/12_master_rosetta_stone_and_notation_guide.ipynb)** | Complete reference guide: side-by-side concept dictionary, notation collision survival guide, 14-formula cheat sheet, and on-call operational runbook. |

---

## 🚀 Getting Started

1. Open JupyterLab at your local instance.
2. Navigate to `conceptual/00_the_physics_of_belief.ipynb` to begin reading.
3. Open `python/00_the_physics_of_belief.ipynb` to run the simulations side-by-side!
