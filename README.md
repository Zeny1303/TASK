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

Expectation and Average (Mean) both describe the central tendency of data, but they differ in how they account for the probability of each value.

---

## 🔹 Average (Mean)
The **average** is a special case of the expected value where all outcomes are equally likely.

Formula:
```
X̄ = μ = (ΣX) / n
```

Where:
- X̄ → Sample mean  
- μ → Population mean  
- ΣX → Sum of all values  
- n → Number of values  

✅ Example (Equal Probabilities):

If X = {1, 2, 3, 4, 5, 6}

```
X̄ = (1 + 2 + 3 + 4 + 5 + 6) / 6 = 3.5
```

---

## 🔹 Expected Value
The **expected value** considers the probability of each outcome.

Formula:
```
E[X] = Σ (X * P(X))
```

Where:
- X → Each possible outcome  
- P(X) → Probability of that outcome  

✅ Example (Unequal Probabilities):

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

---

## 🔹 Key Insight
When all probabilities are equal:
```
E[X] = X̄
```

Otherwise, the expected value differs from the average depending on the probability distribution.

---




 