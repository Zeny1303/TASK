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

---

## Question 5. How Generative Model uses Joint Probability Distribution for generating new data

**Generative Models** are a type of machine learning model that actually *learn how data is formed*, not just how to label or classify it.  
Once they understand how data is generated, they can create new, realistic data that looks like it came from the real world.  

For example – models like **ChatGPT**, **Claude**, or **Grok** are trained on huge amounts of data.  
They learn patterns, context, and relationships between words, and that’s how they can generate meaningful and human-like responses.

---

### **Joint Probability Distribution**

For a set of variables like \( X_1, X_2, ..., X_n \), the **joint probability distribution**  

$$
P(X_1, X_2, ..., X_n)
$$  

tells us the probability of all those variables happening together.  
Basically, it captures how different features in data are related and occur together.

A **Generative Model** tries to learn this joint probability of the training data in such a way that it gets as close as possible to the *real-world probability*:

$$
P_{\text{real}}(X)
$$  

which represents how real data naturally exists.  

The model builds its own understanding of probability, which is written as:

$$
P_{\theta}(X)
$$  

Here, \( θ\) means the parameters of the model (like weights and biases).  
The goal during training is to keep adjusting these parameters until:

$$
P_{\theta}(X) \approx P_{\text{real}}(X)
$$  

So, when both become close enough, it means the model has truly learned the real-world data distribution and that’s when it can start generating new, realistic samples.

---

### **How the Model Generates New Data**

Once the model has learned the patterns from data, it can start generating new data from the probability it has learned.  
Since learning everything at once is complex, most models use **Sequential Generation**, which means generating step-by-step:

1. First, generate \( X_1 \) from \( P(X_1) \)
2. Then generate \( X_2 \) based on \( P(X_2 | X_1) \)
3. Next, generate \( X_3 \) based on \( P(X_3 | X_1, X_2) \)
4. And continue the same for all other variables.

Mathematically, it looks like this:

$$
P(X_1, X_2, ..., X_n) = P(X_1) \times P(X_2 | X_1) \times P(X_3 | X_1, X_2) \times ... \times P(X_n | X_1, X_2, ..., X_{n-1})
$$  

That’s exactly how models like **GPT** generate text  one word at a time, predicting the next word based on all the previous ones.  
Similarly, image-based models like **Diffusion Models** or **VAEs** generate pixels or features step by step to create complete images.


---

## Question 9 . Consider a quiz game where a person is given two questions and must decide which question to answer first. Question 1 will be answered correctly with probability 0.8, and the person will then receive as prize $100, while question 2 will be answered correctly with probability 0.5, and the person will then receive as prize $200. If the first question attempted is answered incorrectly, the quiz terminates (the person is not allowed to attempt the second question). If the first question is answered correctly, the person is allowed to attempt the second question.Which question should be answered first to maximize the expected value of the total prize money received?
## ANSWER : The player should answer the 0.8-probability $100 question before the 0.5-probability $200 question.

Given in Question :-
| Question | Probability of Correct | Prize |
|----------|----------------------|-------|
| Q1       | 0.8                  | $100  |
| Q2       | 0.5                  | $200  |

It is clearly mentioned in question :
1. If the **first question is wrong**, the game ends.  
2. If the **first question is correct**, the player can attempt the second question.  

Here , we need to maximize expected total prize.
So, There are two cases 
#### Case 1:-Answer Q1 first, then Q2
1.Probability Q1 is correct = 0.8 → Win $100
2.Probability Q2 is correct if Q1 was correct = 0.5 → Win additional $200

Expected Value :
```
EV=(Probability Q1 correct)×[Prize for Q1+(Probability Q2 correct×Prize for Q2)]
𝐸𝑉=0.8×[100+(0.5×200)]

𝐸𝑉=0.8×[100+100]=0.8×200
EV = $160
```

#### Case 2: Answer Q2 first, then Q1

Expected Value :
```
EV=(Probability Q2 correct)×[Prize for Q2+(Probability Q1 correct×Prize for Q1)]
𝐸𝑉=0.5×[200+(0.8×100)]

𝐸𝑉=0.8×[200+18]=0.5×280
EV = $140
```
So even though Q2 offers a higher individual prize ($200), the higher probability of Q1 ($100 with 0.8 probability) gives a higher expected value when answered first.

1. If we start with Q2(0.5 probability),there's a 50 % chance that game ends immediately , so we never get the easier amount of $100 from Q1.
2. If we start with Q1 (0.8 probability),there's a high chance secure the smaller prize first, and then we have still a chance to win a bigger prize.
