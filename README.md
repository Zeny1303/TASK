# TASK

## Question 1. Define Sample Probability and Real Probability

**Answer:**  

**Real Probability** — The theoretical probability calculated using the number of favorable outcomes over the total possible outcomes.  

- **Formula:**  
  P(A) = Number of favourable outcomes / Total number of possible outcomes  
- **Example:**  
  When tossing a fair coin:  
  P(H) = 1/2 = 0.5  
- **Notes:**  
  - This probability **does not change**, no matter how many times you toss the coin (100, 200, etc.).  
  - It is based on the **model of fairness**.  

---

**Sample Probability** — The probability calculated from **actual observations** or experimental data.  

- **Formula:**  
  Pₙ(A) = n(A) / N  
  Where:  
  - N = Total number of trials  
  - n(A) = Number of times event A actually occurred  
- **Example:**  
  Tossing a coin 100 times and getting 76 heads:  
  P₁₀₀(H) = 76 / 100 = 0.76  
- **Notes:**  
  - This probability is based on **actual observation** from the sample.  

Hence, **sample probability** is our experimental estimate, while **real probability** represents the ideal theoretical model.

---

## Question 2. Difference Between Expectation and Average

Expectation and Average (Mean) both describe the central tendency of data, but they differ in how they account for the **probability of each value**.

---

### 🔹 Average (Mean)
The **average** is a special case of the expected value where **all outcomes are equally likely**.

**Formula:**
```
X̄ = μ = (ΣX) / n
```

Where:  
- X̄ → Sample mean  
- μ → Population mean  
- ΣX → Sum of all values  
- n → Number of values  

**Example (Equal Probabilities):**  
If X = {1, 2, 3, 4, 5, 6}  
```
X̄ = (1 + 2 + 3 + 4 + 5 + 6) / 6 = 3.5
```

---

### 🔹 Expected Value
The **expected value** considers the **probability** of each outcome.

**Formula:**
```
E[X] = Σ (X * P(X))
```

Where:  
- X → Each possible outcome  
- P(X) → Probability of that outcome  

**Example 1 — Equal Probabilities:**  
If X = {1, 2, 3, 4, 5, 6}  
and  
P(1)=1/6, P(2)=1/6, P(3)=1/6, P(4)=1/6, P(5)=1/6, P(6)=1/6  
Then,  
```
E[X] = 1*(1/6) + 2*(1/6) + 3*(1/6) + 4*(1/6) + 5*(1/6) + 6*(1/6)
E[X] = 3.5
```
Here,  
```
E[X] = X̄
```
because all probabilities are equal.

**Example 2 — Unequal Probabilities:**  
If X = {1, 2, 3, 4, 5, 6}  
and  
P(1)=3/20, P(2)=3/20, P(3)=3/20, P(4)=3/20, P(5)=1/5, P(6)=1/5  
Then,  
```
E[X] = 1*(3/20) + 2*(3/20) + 3*(3/20) + 4*(3/20) + 5*(1/5) + 6*(1/5)
E[X] = 3.7
```

Here,  
```
E[X] = 3.7
X̄ = 3.5
```

Thus, **average** is a special case of **expected value** when all probabilities are equal.

---

## Question 3. Law of the Unconscious Statistician (LOTUS)

### Definition
**LOTUS** stands for **Law of the Unconscious Statistician**.  
It allows us to compute the **expected value of a function of a random variable** without first finding the distribution of that function.

---

### 🔹 Formula

#### For Discrete Random Variables:
```
E[g(X)] = Σ g(x) * P(X = x)
```

#### For Continuous Random Variables:
```
E[g(X)] = ∫ g(x) * f_X(x) dx
```

Where:  
- g(X) → Function of the random variable X  
- P(X = x) → Probability mass function (PMF)  
- f_X(x) → Probability density function (PDF)

---

### 🔹 Intuitive Explanation
To find **E[g(X)]**, you **don’t need to find the distribution of g(X)**.  
You can compute it directly using the **distribution of X**.

---

###  Example (Discrete Case)
If X = {1, 2, 3} with probabilities {0.2, 0.5, 0.3}, and we want E[X²]:  
```
E[X²] = Σ x² * P(X = x)
       = 1²(0.2) + 2²(0.5) + 3²(0.3)
       = 0.2 + 2 + 2.7 = 4.9
```

---

###  Example (Continuous Case)
If X has PDF f(x) = 2x for 0 < x < 1, and we want E[X²]:  
```
E[X²] = ∫₀¹ x² * 2x dx
       = 2 ∫₀¹ x³ dx
       = 2 * (1/4) = 0.5
```

