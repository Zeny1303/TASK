# TASK
## Question 1. Define Sample Probability and Real Probability

**Answer:**  

**Real Probability** - The theoretical probability calculated using the number of favorable outcomes over the total possible outcomes.  
  
- Formula: P(A) = Number of favourable outcomes / Total number of possible outcomes  
- Example: When tossing a fair coin  
  P(H) = 1/2 = 0.5  
- Notes:  
  - This probability **does not change**, no matter how many times you toss the coin (100 times, 200 times, etc.)  
  - Based on the **model of fairness**  

**Sample Probability** is calculated from **actual observations**. 
- Formula: P_n(A) = n(A) / N  
 Where
  - N = Total number of trials  
  - n(A) = Number of times event A actually occurred  
- Example: Tossing a coin 100 times and getting 76 heads  
  P100(Head) = 76 / 100 = 0.76  
- Notes:  
  - This probability is based on **actual observation** from the sample
Hence, sample probability is our experimental estimate, while real probability represents the ideal theoretical model.

## Question 2 .Difference Between Expectation and Average

**Expectation** and **Average (Mean)** both describe the *central tendency* of a dataset, but they differ in how they handle **probabilities** of each value.

## 🔹 Average (Mean)
The **average** is a *special case* of the **expected value**, where **all outcomes are equally likely**.

\[
\bar{X} = \mu = \frac{\sum X}{n}
\]

- **\(\bar{X}\)** → Sample mean (from a sample)
- **\(\mu\)** → Population mean
- **\(\sum X\)** → Sum of all observed values
- **\(n\)** → Total number of observations

### ✅ Example (Equal Probabilities)
If \( X = \{1, 2, 3, 4, 5, 6\} \):

\[
\bar{X} = \frac{1 + 2 + 3 + 4 + 5 + 6}{6} = 3.5
\]

---

## 🔹 Expected Value (Mathematical Expectation)
The **expected value** accounts for **unequal probabilities** of outcomes.

\[
E[X] = \sum_{i=1}^{n} X_i \cdot P(X_i)
\]

- **\(X_i\)** → Random variable outcomes  
- **\(P(X_i)\)** → Probability of each outcome  

###  Example (Unequal Probabilities)
Let \( X = \{1, 2, 3, 4, 5, 6\} \) and:

\[
P(1)=\frac{3}{20},\; P(2)=\frac{3}{20},\; P(3)=\frac{3}{20},\; P(4)=\frac{3}{20},\; P(5)=\frac{1}{5},\; P(6)=\frac{1}{5}
\]

Then:

\[
E[X] = 1\cdot\frac{3}{20} + 2\cdot\frac{3}{20} + 3\cdot\frac{3}{20} + 4\cdot\frac{3}{20} + 5\cdot\frac{1}{5} + 6\cdot\frac{1}{5} = 3.7
\]

Here:

\[
E[X] = 3.7 \quad \text{while} \quad \bar{X} = 3.5
\]

---

## 🔹 Key Insight

> When all probabilities are **equal**,  
> \[
> E[X] = \bar{X}
> \]
> Otherwise, the **expected value differs** from the **simple average** depending on the probability distribution.



 