# Decision-Analytics
Loan or Bonds? - Bank Decision Analysis (Strategy Report)
# Decision Analytics: Loan vs. Bond Strategy
### Optimizing Capital Allocation using Bayesian Revision

## 📌 Project Overview
This project analyzes a $200,000 capital allocation dilemma for a commercial bank. The goal is to determine whether to invest in a high-yield loan (8%) with default risk or a guaranteed bond (6%). 

By implementing a **Sequential Decision Tree**, I evaluated the impact of acquiring "Sample Information" (a credit consultation) to update prior beliefs about customer default and maximize Expected Value (EV).

## 🧮 The Mathematics of Uncertainty
The core of this analysis relies on **Bayes' Theorem** to convert prior probabilities into posterior probabilities based on the reliability of the credit consultation.

### 1. Prior Probabilities
*   **P(Default) = 0.04**
*   **P(Not Default) = 0.96**

### 2. Conditional Probabilities (Test Reliability)
The consultation is imperfect but historically reliable:
*   **P(Favorable | Not Default) = 0.775**
*   **P(Favorable | Default) = 0.150**

### 3. Calculating Posterior Probabilities (The Nodes)
To find the probability of default *given* a favorable report—**P(Default | Favorable)**—we use:

$$P(D|F) = \frac{P(F|D) \times P(D)}{[P(F|D) \times P(D)] + [P(F|ND) \times P(ND)]}$$

Substituting the values:
*   $P(D|F) = \frac{0.15 \times 0.04}{(0.15 \times 0.04) + (0.775 \times 0.96)}$
*   $P(D|F) = \frac{0.006}{0.006 + 0.744}$
*   **P(Default | Favorable) ≈ 0.008 (0.8%)**  <-- *This matches the node in my tree!*

Similarly, for an **Unfavorable** report, the default risk jumps to **13.6%**, making the bond the mathematically superior choice.

## 🚀 Key Results
*   **EV without Info (EVwoSI):** $12,000 (Bonds)
*   **EV with Sample Info (EVwSI):** $13,204 (After $500 fee)
*   **EV of Sample Information (EVSI):** $1,704

**Conclusion:** The bank should always conduct the consultation as it yields a net benefit of $1,204 over the next best alternative.

## 📂 Repository Contents
*   `Decision_Tree_Analysis.png`: High-resolution visual of the strategy.
*   `Bayes_Calculations.xlsx`: Step-by-step probability revision table.
