# TASK

## Question 1. Define Sample Probability and Real Probability

**Answer:**  

**Real Probability** - The theoretical probability calculated using the number of favorable outcomes over the total possible outcomes.  

- **Formula:**  
  P(A) = Number of favourable outcomes / Total number of possible outcomes  
- **Example:**  
  When tossing a fair coin:  
  P(H) = 1/2 = 0.5  
- **Notes:**  
  - This probability **does not change**, no matter how many times you toss the coin (100, 200, etc.).  
  - It is based on the **model of fairness**.  

---

**Sample Probability** - The probability calculated from **actual observations** or experimental data.  

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



---

### 🔹 Average 
The **average** is the sum of observed outcomes divided by the number of observations. 

**Formula:**
```
X̄  = Σ(X) / n
```

Where:  
- X̄ → Sample mean   
- ΣX → Sum of all values  
- n → Number of values  

**Example (Equal Probabilities):**  
If X = {1, 2, 3, 4, 5, 6}  
```
X̄ = (1 + 2 + 3 + 4 + 5 + 6) / 6 = 3.5
```

---

### 🔹 Expectation
It refers to the  result that will be seen if the same random experiment of a random variable is done multiple times, like rolling a dice or tossing a coin, is repeated many times under the same condition. Over lots of tries, the average of all results end up close to the expectation.

**Formula:**
```
E[X] = Σ (X * P(X ))
```

Where:  
- X → Random Variable
- P(X) → Probability of Random Variable  

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



---

## Question 3. What do you mean by subspace?
A subspace is a subset of a vector space that itself satisfies all the properties necessary to be a vector space. This means a subspace must:

1. Contain the zero vector,
2. It should be closed under vector addition and scalar multiplication.

For example -
Let V be a vector space and R be a subset of V. Then R is a subspace of V if 
1. The zero vector must be present in R, i.e, 0 belongs to R.
2. For any vectors u and v that belong to R, the set R should be closed under addition, meaning **u+v belongs to R**.
3. For any vector u that belongs to R and scalar a, the set R should be closed under scalar multiplication, **au belongs to R**.

---

## Question 4. Law of the Unconscious Statistician (LOTUS)

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

So, when both become close enough, it means the model has truly learned the real-world data distribution, and that’s when it can start generating new, realistic samples.

---

***Gmail’s Spam Filter (Generative Approach)***
Let’s imagine Gmail’s AI model is learning from millions of emails.It looks at both the content and the label (spam or not spam).The model is a generative model, meaning it wants to learn:
```
[
P(X, Y) = P(Y) \times P(X|Y)
]
```
where:
• ( Y ) = label (spam / not spam)
• ( X ) = the words, structure, and style of the email

Email 1 — Spam

Subject: Congratulations! You have won $1000 cash prize

Body:
Dear user,
You have been selected as one of our lucky winners!
Click the link below to claim your cash reward.
Offer valid for 24 hours only.
**Label: Spam**


Email 2 — Spam
Subject: Limited-time offer on loan approval

Body:
Get instant loan approval with zero interest.
Apply now and receive money directly in your account.
Don't miss this special offer.
**Label: Spam**

Email 3 — Not Spam

Subject: Project meeting at 10 AMBody:

Hi team,
Please join the project discussion meeting at 10 AM tomorrow.
We will review the progress report and plan next steps.
**Label: Not Spam**

Email 4 — Not Spam

Subject: Office maintenance schedule
Body:
Dear employees,
The office will be closed for maintenance work on Saturday.
Please plan your tasks accordingly.
**Label: Not Spam**

What the Model Learns (Joint Distribution)
Now the model studies both the email content and label.

It learns the joint probability ( P(X, Y) ) — which captures:

• What kinds of words and styles appear in spam,
• What kinds appear in normal work-related emails.

From these, it estimates probabilities like:

| Word | P(word | Spam) | P(word | Not Spam) |
|------|----------------|------------------|
| “win” | 0.7 | 0.02 |
| “offer” | 0.6 | 0.1 |
| “loan” | 0.5 | 0.05 |
| “click” | 0.4 | 0.05 |
| “project” | 0.05 | 0.7 |
| “meeting” | 0.02 | 0.6 |
| “report” | 0.05 | 0.5 |
| “dear” | 0.6 | 0.4 |
| “money” | 0.5 | 0.1 |

It also learns priors:

This means:

About 40% of emails are spam, and they frequently contain words like win, offer, click, money.
60% are normal, containing words like project, meeting, report.


Here as we know our model is trained on previous dataset so it can tell which mail is spam and which one is not so now we generate some random combinations of sentences and give it to our model for testing and if it suits and not spam then it will be considered as the successfully generated data.

The Generated Email (Spam Example)

Subject: Special offer! Win easy money today

Body:

Dear customer,
You have a special chance to win big money instantly!
Click the link below to claim your offer before it expires.
Act now to secure your reward.

This email was never seen before, yet it looks realistic and spammy.
It was generated entirely by sampling from P(X,Y).
Analyzing How It Was Generated
Step What Happened Probability Used

1 The model picked “Spam” as the category ( P(Y=\text{spam}) = 0.4 )

2 Then sampled “win”, “offer”, “click”, “money”, “dear” from ( P(X))

3 It skipped “meeting” and “project”
because their spam likelihood was
lowStep What Happened Probability Used

4 Combined selected words into a sentence using
learned grammar patterns
(from text structure in training
data)

5 Result = realistic spam message
drawn from the learned joint
distribution

The joint probability distribution ensured that:
• Spam-like words appeared together more often,
• Work-related words stayed out of the message,
• And the final message matched what spam typically looks like.

Generated Email (Not Spam Example)
Subject: Project meeting report
Body:

Dear team,

Please attend the project meeting tomorrow morning.
We will discuss the progress report and upcoming deadlines.

This one also looks completely natural — but businesslike, not spammy.

SO HERE YOU CAN SEE EXAMPLE OF SUCCESSFUL GENERATED DATA


---

## Question 6. Why Companies always train their model on the Large Data?

Companies train their models on large datasets because large data helps them estimate the *true expectation* of outcomes more accurately.
In machine learning, a model tries to learn the expected value (E[Y|X]) .
 for example, the probability that an email is spam given its features. With a small dataset, this estimated expectation can fluctuate a lot due to limited samples, leading to biased or unstable predictions.

For instance, if Gmail trained its spam filter on just a few hundred emails, it might wrongly learn that any message with the word “win” is always spam. But if it trains on millions of emails, it sees many variations — some with “win” that are spam and some that aren’t — and thus learns a more reliable expected probability (P(\text{spam}|X)).

By the **Law of Large Numbers**, as the amount of data increases, the model’s estimated expectations converge to the true expectations. This means large datasets help models capture real patterns instead of noise, leading to more accurate, stable, and generalizable predictions in real-world applications.

---

## Question 9 . Consider a quiz game where a person is given two questions and must decide which question to answer first. 
Question 1 will be answered correctly with probability 0.8, and the person will then receive as prize $100, while question 2 will be answered correctly with probability 0.5, and the person will then receive as prize $200. If the first question attempted is answered incorrectly, the quiz terminates (the person is not allowed to attempt the second question). If the first question is answered correctly, the person is allowed to attempt the second question.Which question should be answered first to maximize the expected value of the total prize money received?

**ANSWER** : The player should answer the 0.8-probability $100 question before the 0.5-probability $200 question.

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

𝐸𝑉=0.8×[200+80]=0.5×280
EV = $140
```
So even though Q2 offers a higher individual prize ($200), the higher probability of Q1 ($100 with 0.8 probability) gives a higher expected value when answered first.

1. If we start with Q2(0.5 probability),there's a 50 % chance that game ends immediately , so we never get the easier amount of $100 from Q1.
2. If we start with Q1 (0.8 probability),there's a high chance secure the smaller prize first, and then we have still a chance to win a bigger prize.