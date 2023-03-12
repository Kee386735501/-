## COMP21111 Logic and Modelling  



### 1.Introduction/Propositional Logic 



#### 1.1 Why Propositional Logic?

- Propositional logic is a **foundation** for most of the more expressive logics
- Propositional logic is one of the **simplest** logics yet has many computational challenges
- Propositional logic has **direct applications** e.g. circuit design, verification, mathematics . . .
- There are **efficient algorithms for reasoning** in propositional logic

#### 1.2 What is logic?

-  **Syntax**: formal language

- **Semantics**: meaning for the language

- **Reasoning**:
  - Proof theory
  - Model theory

#### 1.3 Propositional (Boolean) Logic

*Example: ”**If** I study hard **and** I complete all assignments **then** I will get a good grade.” (*)*

**Atomic propositions:**

- I study hard
- I complete all assignments
- I will get a good grade

From atomic propositions we can construct more complex propositions (formulas) using Boolean connectives (**and, or, not,...**).

Propositions can be **true** or **false** depending on the value atomic propositions.

#### 1.4 Syntax: Propositional Formulas

**Propositional (Boolean) variables** usually denoted as **p, q, s, . . ..**

Connectives: ∧ “and”, ∨ “or”, ¬ “not”, → “implies”, ↔ “equivalent/bi-implication”

**Propositional formula:**

- Every propositional variable is a formula, also called **atomic formula**, or simply **atom**.

- T (true) and ⊥ (false) are formulas. 

- I If A1, . . . , An are formulas, where n ≥ 2, then (A1 ∧ . . . ∧ An) and (A1 ∨ . . . ∨ An) are formulas. 

- I If A is a formula, then ¬A is a formula.

-  I If A and B are formulas, then (A → B) and (A ↔ B) are formulas.

#### 1.5 Subformulas

Example: ((p ∧ q)→(q ∨ ¬p ∨ s))

**Immediate Subformulas:**

(p ∧ q) and (q ∨ ¬p ∨ s)

**Subformulas:**

((p ∧ q)→(q ∨ ¬p ∨ s));

 (p ∧ q) and (q ∨ ¬p ∨ s); 

p; q; ¬p; s

**Notation**: **A[B]** means **B** occurs in **A** as a subformula

#### 1.6 Connectives and their precedence

Example: ((p ∧ q) → (q ∨ ¬p ∨ s)) (too many brackets...)

![image-20230123155106965](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123155106965.png)

*Now we can replace*

 **((p ∧ q) → (q ∨ ¬p ∨ s))** with **p ∧ q → q ∨ ¬p ∨ s**



##### 1.6.1Parsing Formulas

Let us parse 

​								**¬A ∧ B → C ∨ D ↔ E.**

Inside-out (starting with the highest precedence connectives):

​                               **((¬A ∧ B) → (C ∨ D)) ↔ E**



Outside-in (starting with the lowest precedence connectives):

​								**((¬A ∧ B) → (C ∨ D)) ↔ E.**

#### 1.7 Semantics: Interpretation

An ***interpretation** I* assigns truth values to propositional variables

 								**I : P → {1, 0}**

**1, 0** are called truth values or also Boolean values.

-  If I(p) = 1, then p is called **true** in I.
- If I(p) = 0, then p is called **false** in I.

Interpretations are also called ***truth assignments***.

*Example: I(p) = 0; I(q) = 1; I(s) = 0*

##### 1.7.1 Evaluating formulas

*The **truth value of a complex formula** is uniquely determined by the truth values of its components.*

Given an interpretation I, extend I to a mapping from all formulas to truth values as follows.

1. **I(T) = 1** and **I(⊥) = 0**
2. **I(A1 ∧ . . . ∧ An) = 1** if and only if **I(Ai) = 1** for **all i**.
3. **I(A1 ∨ . . . ∨ An)** **= 1** if and only if I(Ai) = 1 for **some i**.
4. I**(¬A) = 1** if and only if **I(A) = 0**.
5. **I(A1 → A2) = 1 if and only if I(A1) = 0 or I(A2) = 1**.
6. **I(A1 ↔ A2) = 1 if and only if I(A1) = I(A2)**.

![image-20230123160548849](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123160548849.png)



#### 1.8 Truth Tables

![image-20230123160624400](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123160624400.png)

#### 1.9 Operation tables

![image-20230123160738050](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123160738050.png)

##### 1.9.1 How to evaluate a formula?

Let’s evaluate the formula

​				*((p → q) ∧ ((p ∧ q) → r)) → (p → r)*

in the interpretation

​					*I = {p 7→ 1, q 7→ 0, r 7→ 1}.*

![image-20230123160946130](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123160946130.png)

### 2.Satisfiability (propositional logic)

#### 2.1 Satisfiability, validity

-  If a formula A is **true** in **I** we say that **I satisfies A** and that I is a model of A, denoted by **I |= A**.
-  If a formula A is **false** in I then I does **not satisfy A**, denoted **I |≠ A**.
- A is **satisfiable** if A is **true** in **some interpretation**
- A is **unsatisfiable**, denoted **A |= ⊥**, if A is **false** in **all** interpretations.
- A is **valid** (or a **tautology**) if A **true** in **every interpretation** denoted |= A.
- A formula A **entails** B, (denoted A |= B) if **all models of A are models of B.**
- Two formulas A and B are called **equivalent**, (denoted A ≡ B) if they have the **same models.**

#### 2.2Truth Tables

Consider ***A = p ∧ ¬q → q ∨ ¬p.*** 

We know how to calculate the truth value of A in an interpretation I. 

E.g. If *I = {p = 0; q = 0} then I(A) = 1*.

 Now we consider **all** possible interpretations:

![image-20230123162411206](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123162411206.png)

**Q: Is p ∧ ¬q → q ∨ ¬p equivalent to ¬p ∨ q ?** 

**Summary**: Using truth tables we can check **satisfiability, validity and equivalence**.

**Limitations**: For a modest number of variables truth tables are unacceptably huge!

![image-20230123162752256](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123162752256.png)

![image-20230123162826385](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123162826385.png)

#### 2.3 Connections between these notions

1. A formula A is **valid** if and only if **¬A is unsatisfiable**.

2. A formula A is **valid** if and only if **A is equivalent to** T

3. A formula A is **satisfiable** if and only if **¬A is not valid**.

4. A formula A is **satisfiable** if and only if **A** **is not equivalent to ⊥**.

5. Formulas **A and B are equivalent** if and only if the **formula A ↔ B is valid**.

6. Formulas **A and B are equivalent** if and only if the **formula ¬(A ↔ B) is unsatisfiable**

7. Propositional **satisfiability** is **NP-complete**. 

8. Propositional **validity** is **coNP-complete**.

   ​           

   

   

#### 2.4 Equivalent replacement

Notation:

- DenoteA[B] a formula **A** with a **fixed occurrence of a subformula B**.
- Given A[B], denote **A[B’]** the formula obtained from A by **replacing this occurrence of B by B’**.

**Lemma (Equivalent Replacement)**

*Let I be an interpretation and **I |= A1 ↔ A2. Then I |= B[A1] ↔ B[A2].***

***In other words, replacing, in a formula B, a subformula A1 by a formula A2 with the same value gives a formula with the same value.***

**Theorem (Equivalent Replacement)**

Let A1 ≡ A2. Then B[A1] ≡ B[A2].

**In other words, replacing, in a formula B, a subformula A1 by an equivalent formula A2 gives an equivalent formula.**

#### 2.5 A purely syntactic algorithm for evaluation

We know a **semantic** algorithm for evaluation of a formula on an **interpretation I.**

Now we will study a **syntactic** algorithm for evaluation. 

Assume ***I*** and we evaluate formula ***A[p]*** on ***I***.

Observe:

-   If I |= p, then I |= p ↔ >; 
-  If I |≠ p, then I |= p ↔ ⊥;

**Since we can replace a subformula by a formula with the same value, we can replace every atom p by either T or ⊥, depending on the value of p in I.**

#### 2.6 Rewrite rules for evaluating a formula

 Suppose that we have a formula **consisting only** of ⊥ and T. 

One can note that every formula of this form different from ⊥ and T can be **“simplified”** **to a smaller equivalent** formula. 

For example, every formula of the form **A → T** is equivalent to a simpler **formula T**. 

This **simplification process** can be formalised as a **rewrite rule system**:

![image-20230123164717092](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123164717092.png)

#### 2.7 Algorithm for evaluating a formula

We can define a purely syntax algorithm for evaluating a formula using the rewrite rule system.

![image-20230123164936411](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123164936411.png)

**Example**

Let us evaluate the formula 

​							(p → q) ∧ (p ∧ q → r) → (p → r)

in the interpretation

​                              {p |→ 1, q |→ 0, r |→ 1}.

 Its value is equal to the value of

​                    (T → ⊥) ∧ (T ∧ ⊥ → T) → (T → T)

**Apply rewrite rules**

![image-20230123165718287](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123165718287.png)



#### 2.8 The splitting algorithm for propositional satisfiability

![image-20230124143813874](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124143813874.png)

##### 2.8.1 Simplification rules for T and ⊥

![image-20230124144013530](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124144013530.png)

##### 2.8.2 Splitting Algorithm

splitting 算法 

![image-20230124144223597](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124144223597.png)

**example**

splitting tree   

逐步带入变量p，q，r.. 并赋值最后得到 真和假  

![image-20230124144356710](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124144356710.png)

##### **2.8.2Monotonicity, position, polarity**，pure atom

###### Monotonicity  

单调性 

**也就是 从x1 到 xn 中 的某个 xk 带入 0 时比带入1 小 则为monotonic** 

**反之则 为 anti-monotonic** 

![image-20230124144741567](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124144741567.png)

**Monotonicity and logical connectives**

-  The connectives **∧** and **∨** are monotonic on all of their arguments. 

- The negation **¬ is anti-monotonic.** 

- The implication **→ is monotonic on its second argument**, but anti-monotonic on its first argument. 

- The equivalence ↔ is **neither monotonic nor anti-monotonic** on either of its arguments. on either of its arguments.

  ***交并都monotonic ，  imply  第一个输入 anti-monotonic  第二个输入monotonic***

  ***double imply 既不 monotonic 也不 anti-monotonic***

###### Parse tree

![image-20230124145945368](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124145945368.png)

position  就是线上的 数字顺着写就行

###### Positions and Subformulas

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124150426154.png" alt="image-20230124150426154" style="zoom:67%;" />

###### Polarity

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124150555233.png" alt="image-20230124150555233" style="zoom:67%;" />

###### The coloring algorithm for determining polarity

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124150907059.png" alt="image-20230124150907059" style="zoom:67%;" />

***画出splitting tree 之后 标出箭头上的数字，negation 和 imply 的左边 都是红色的 ，如果红色箭头个数为奇数则极性为-1*** 

***偶数的话则为1*** 

***double imply 是蓝色   ，equivalence，  polarity是 0*** 

###### Connection between  imply and ltq 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124151521685.png" alt="image-20230124151521685" style="zoom: 67%;" />

###### Monotonic replacement lemma

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124151648418.png" alt="image-20230124151648418" style="zoom:67%;" />

###### Pure Atom  

​						<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124152129882.png" alt="image-20230124152129882" style="zoom:67%;" />

如果 p 在 A 中为 pure Atom 则  所有的  p 在A 中的polarity  都是 1 或者 -1 也就是有红线

###### Proverties of  pure Atoms 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124153050205.png" alt="image-20230124153050205" style="zoom:67%;" />

**当 A 中存在 pure Atom p时 A 是 satisfiable** 

###### Pure atom rule, example

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124153149492.png" alt="image-20230124153149492" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124153237871.png" alt="image-20230124153237871" style="zoom:67%;" />

All occurrences of r are negative, so, for the purpose of checking satisfiability we can replace r by ⊥.

We have shown satisfiability of this formula deterministically, using only the pure atom rule

### 3.CNF/formalisations 

####  3.1 Literal, clause

- **Literal**: either an atom **p** (positive literal) or its negation **¬p** (negative literal).
- The **complementary literal to** L:

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123170422766.png" alt="image-20230123170422766" style="zoom: 50%;" />

​               In other words, p and ¬p are complementary.

-  **Clause**: a disjunction. **L1 ∨ . . . ∨ Ln, n ≥ 0 of literals.** 

  - **Empty clause,** denoted by  ⬜: n = 0 (the empty clause is false in every interpretation).
  - **Unit clause**: n = 1.
  - **Horn clause**: a clause with at most one positive literal.

  ​     

#### 3.2 CNF

- A formula *A* is in ***conjunctive normal form***, or ***simply CNF***, if it is either T, or ⊥, or a conjunction of disjunctions of literals:

  ![image-20230123171253346](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123171253346.png)

- **A formula B** is called a **conjunctive normal form of a formula** A if B is equivalent to A and B is in conjunctive normal form.                  

##### 3.2.1 Satisfiability of CNF 

- An interpretation I satisfies a formula in CNF

   ![image-20230123172636876](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123172636876.png)

  if and only if it **satisfies every clause in it** 

  ![image-20230123172727220](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123172727220.png)

- An interpretation I **satisfies a clause** 

  ​        **L1 ∨ . . . ∨ Lk**

​               if and only if it satisfies **at least** one literal Lm in this **clause**.

####            3.3 The Standard CNF transformation ![image-20230123173332591](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123173332591.png)

 ![image-20230123173511290](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123173511290.png)

#### 3.4 CNF and satisfiability

​                    ¬((p → q) ∧ (p ∧ q → r) → (p → r)) ⇒

​														· · ·

​                          (¬p ∨ q) ∧ (¬p ∨ ¬q ∨ r) ∧ p ∧ ¬r

Therefore, the formula 

​					¬((p → q) ∧ (p ∧ q → r) → (p → r))

has the same models as the set consisting of four clauses

 								¬p ∨ q

​								 ¬p ∨ ¬q ∨ r 

​									p 

​                                    ¬r

The CNF transformation **reduces the satisfiability problem for formulas to the satisfiability problem for sets of clauses**.

#### 3.5 Definitional clausal form transformation

##### 3.5.1 Problem with standard CNF transformation

compute CNF of  

![image-20230123174219817](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123174219817.png)

if we continue, the formula will **grow exponentially**

##### 3.5.2 CNF is exponential

s there any way to avoid exponential blowup? **No** 

There are formulas for which the shortest CNF has an **exponential size**.

**Approach**: relax requirement of **equivalence** preserving to **equisatisfiability** preserving.

##### 3.5.3 Idea

Using so-called **naming** or **definition introduction**.

- Take a **non-trivial** subformula **A**

- Introduce a new name ***n*** for it. A name is a new propositional variable.

- Add a formula stating that ***n*** is equivalent to A (***definition for*** n)

  p1 ↔ **(p2 ↔ (p3 ↔ (p4 ↔ (p5 ↔ p6))))** 

  **n** ↔ **(p5 ↔ p6)**

- Replace the subformula by its name:

  p1 ↔ (p2 ↔ (p3 ↔ (p4 ↔ n))) 

  n ↔ (p5 ↔ p6)

This set is **not equivalent** to the original formula but **equisatisfiable** (satisfible if and only if the original formula is).

After several steps

![image-20230123181054182](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123181054182.png)

#### 3.6 Clausal Form

- **Clausal form** of a formula A: a set of clauses which is **satisfiable** if and only if A is **satisfiable**

  如果 formula A 是 satisfiable 的话  A的所有 clause 都是 satisfiable

- **Clausal form** of a set S of formulas: a set of clauses which is **satisfiable** if and only if so is S.

Using **clausal normal forms** instead of **conjunctive normal forms** we can convert any formula to an **equisatisfiable set** of clauses with at most linear increase in the size of the formula.

##### 3.6.1 Definitional clausal form transformation

**Theorem**

​	            **F[G] is satisfiable ⇔ F[n] ∧ (n ↔ G) is satisfiable**

provided n is a (fresh) propositional variable not occurring in F[G]. n can be seen as a name for G.

**Definitional clausal clausal form transformation:**

- introduce names for every non-literal subformula in the original formula (this introduces a linear number of new symbols),
- replace subformulas by their names and add corresponding definitions,
- transform definitions into sets of clauses using the standard transformation

**Definitional clausal form transformation (proof)**

Assume F[n] ∧ (n ↔ G) is satisfiable

Then, there exists an interpretation I such that I |= F[n] ∧ (n ↔ G). We need to show that F[G] is satisfiable.

Indeed, take I then by **Equivalence Replacement Lemma** we have I |= F[G].

we shown 

**Theorem**. Any **propositional formula** can be transformed into an **equisatisfiable clausal normal form** by applying the **definitional clausal form transformation**. Moreover, the **size** of the resulting clause set is linear in the size of the formula and each clause contains at most three literals (3-CNF)

If we introduce a name for a subformula and the occurence of the subformula is **positive** or **negative**, then an implication is used instead of equivalence, if it is neutral then we use equivalence..

Lemma.(Positive Definition) Let A[B]π where pol(A, π) is positive. Then A[B]π is satisfiable if and only if A[n] ∧ (n → B) is satisfiable, (where n is a new variable that does not occur A[B]π).

Lemma. (Negative Definition) Let A[B]π where pol(A, π) is negative. Then A[B]π is satisfiable if and only if A[n] ∧ (B → n) is satisfiable, (where n is a new variable that does not occur A[B]π).

#### 3.7 Formalising problems using propositional logic

Suppose we have variables v1, . . . , vn and want to express that exactly k of them are true. 

These formulas are very useful for encoding various problems in SAT. We will write this property as a formula T=k (v1, . . . , vn).

**Expressing Properties “k out of n variables are true”**

Suppose we have variables **v1, . . . , vn** and want to express that exactly **k of them are true**. These formulas are very useful for encoding various problems in SAT. We will write this property as a formula **T=k (v1, . . . , vn).**

First, let us express some simple special cases: 

T=0(v1, . . . , vn) def = ¬v1 ∧ . . . ∧ ¬vn 

T=1(v1, . . . , vn) def = (v1 ∨ . . . ∨ vn) ∧ V i

**To define Tk for 0 < k < n, introduce two formulas:**

- T≤k (v1, . . . , vn): **at most** k variables among v1, . . . , vn are true, where k = 0 . . . n − 1;
- T≥k (v1, . . . , vn): **at least** k variables among v1, . . . , vn are true, where k = 1 . . . n;

![image-20230124140220528](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124140220528.png)

### 4.DPLL: satisfiability algorithm for formulas in clausal normal form

##### 4.1 DPLL: satisfiability of clausal normal forms

​       Satisfiability-checking for sets of clauses

​        <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124162655017.png" alt="image-20230124162655017" style="zoom:67%;" />

##### 4.2 Unit Propogation 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124162923683.png" alt="image-20230124162923683" style="zoom:67%;" />

##### 4.3 DPLL = splitting + unit propagation

​							<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124164352592.png" alt="image-20230124164352592" style="zoom:67%;" />

##### 4.4 DPLL trees

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124164439256.png" alt="image-20230124164439256" style="zoom:67%;" />

​                             <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124164559988.png" alt="image-20230124164559988" style="zoom: 67%;" />

##### 4.5 Optimisation: tautology elimination

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124164658564.png" alt="image-20230124164658564" style="zoom:66%;" />

#####     4.6 Pure literal elimination

​                      <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124164820148.png" alt="image-20230124164820148" style="zoom: 67%;" />

######       Example：

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124164952235.png" alt="image-20230124164952235" style="zoom:50%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124165145976.png" alt="image-20230124165145976" style="zoom:50%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124165255766.png" alt="image-20230124165255766" style="zoom:50%;" />

##### 4.7 Horn clauses

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124165347564.png" alt="image-20230124165347564" style="zoom:50%;" />

​      **Satisfiability of Horn clauses can be decided by unit propagation**

​      <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124165620148.png" alt="image-20230124165620148" style="zoom:50%;" />

##### 4.8 SAT and k-SAT

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124170722539.png" alt="image-20230124170722539" style="zoom:50%;" />

###### 4.8.1Random Clause Generation

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124171037222.png" alt="image-20230124171037222" style="zoom: 67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124171237961.png" alt="image-20230124171237961" style="zoom:67%;" />

​                                       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124171510081.png" alt="image-20230124171510081" style="zoom:50%;" />   

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124171600455.png" alt="image-20230124171600455" style="zoom:60%;" />

### 5.Randomized alg/Tableaux

#### 5.1 SAT as a Decision Problem

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124172709167.png" alt="image-20230124172709167" style="zoom:67%;" />

1. 1.有 yes 和no 作为answer的 problem collection 都是 descision problem , problem 中的 每个element 都被叫做

2. instance 

3. 2 SAT 也是 decision problem ，yes 和 no 是 satisfiable 和 unsatifiable  

4. 3.witness 则是在 polynomial 时间 内 观测 data D 的answer 为 yes 

5. 4.satisfiability 有 small witnesses ：interpretations 

6. 5.unsatisfiability 则是 no-polynomial time 的 witnesses

#### 5.2 Satisfiability Algorithn that Cannot Establish Unsatisfiability         

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124174401064.png" alt="image-20230124174401064" style="zoom:50%;" />

#### 5.3 Randomised Algorithms for SAT

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124174501689.png" alt="image-20230124174501689" style="zoom: 50%;" />

#### 5.4 GSAT(Alg)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124213618016.png" alt="image-20230124213618016" style="zoom:67%;" />

​	 GSAT 算法：randomly 取 I 然后 判断是否能够 satisfy  S , 如果能够则 return I 

​      不能则 依次  flip I 中的 一个 variable p  然后再选择满足最多clauses的variable 保持当前的值再进行下一次flip进行判断

**GSAT  Example** 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124214155369.png" alt="image-20230124214155369" style="zoom:67%;" />

#### 5.5 GSAT with random walks (Alg)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124214744600.png" alt="image-20230124214744600" style="zoom:67%;" />

#### 5.6 GSAT WALKS （Alg）

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124214829308.png" alt="image-20230124214829308" style="zoom:67%;" />

​        **GSAT WALKS EXAMPLE**   

 		<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124215014608.png" alt="image-20230124215014608" style="zoom:67%;" />

​        ***相比较于GSAT, GSAT WALK 在将所有variable flip并统计之后 取出了其中的 unsatisfied clause  再randomly 选这个clause 里面的 variable 来 flip***

#### **5.7 Satisfiability of formulas: Semantic Tableaux**

**5.7.1 Signed Formula**

![image-20230124220344917](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124220344917.png)

##### **5.7.2 Tableau**

![image-20230124220756927](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124220756927.png)

 Tabeau:  由 signed formulas 作为 nodes  构成的tree  

##### 5.7.3 Branch Expansion Rules

![image-20230124221108317](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124221108317.png)

**5.7.4 Branch Closure Rules**

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124225642989.png" alt="image-20230124225642989" style="zoom:67%;" />

Example 1 

 <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124225802122.png" alt="image-20230124225802122" style="zoom:67%;" />

Example 2 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124225943897.png" alt="image-20230124225943897" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124231302337.png" alt="image-20230124231302337" style="zoom:67%;" />

**5.7.4 Checking Other Properties with Tableaux**

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124231615848.png" alt="image-20230124231615848" style="zoom:67%;" />

当 open branch 对于 A = 1 存在时 则为 satisfiable  

​      如果 A =0 是 close branch  则 为valid 

   A 和 B equivalent 如果 存在 

##### 5.7.5 Extras: Flat View of Tableaux 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124232242274.png" alt="image-20230124232242274" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230124232823792.png" alt="image-20230124232823792" style="zoom:67%;" />



### 6.BDT/BDD/OBDD

#### 6.1 Data Structures for Large Propositional Formulas

 <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125001500318.png" alt="image-20230125001500318" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125002222205.png" alt="image-20230125002222205" style="zoom:67%;" />

#### 6.2 Decision Tree 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125002454444.png" alt="image-20230125002454444" style="zoom:67%;" />

​         1 为 实线，0为虚线 ， 节点用圆圈表示

Tests correspond to “if-then-else” 

  <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125002623689.png" alt="image-20230125002623689" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125002706045.png" alt="image-20230125002706045" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125002941123.png" alt="image-20230125002941123" style="zoom:67%;" />

#### 6.3 If-Then-Else Normal Form

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125003134482.png" alt="image-20230125003134482" style="zoom:67%;" />

#### 6.4  Evaluating the Formula

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125003300847.png" alt="image-20230125003300847" style="zoom:67%;" />

#### 6.5 Properties (BDT)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125003447484.png" alt="image-20230125003447484" style="zoom:67%;" />

#### 6.6 Algorithm for Building Binary Decision Trees

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125003637971.png" alt="image-20230125003637971" style="zoom:67%;" />

Example 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125003734081.png" alt="image-20230125003734081" style="zoom:67%;" />

​     Are BDT compact ?

​    <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125004429269.png" alt="image-20230125004429269" style="zoom:67%;" />

  6.7  Binary Decision Diagrams

​    <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125004535407.png" alt="image-20230125004535407" style="zoom:67%;" /> 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125004810493.png" alt="image-20230125004810493" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125004837442.png" alt="image-20230125004837442" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125004859388.png" alt="image-20230125004859388" style="zoom:67%;" />

#### 6.7 Properties(BDD)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125005002386.png" alt="image-20230125005002386" style="zoom:67%;" />

#### 6.8 OBDD  (Ordered Binary Decision Diagrams (OBDDs))

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125005217067.png" alt="image-20230125005217067" style="zoom:67%;" />

6.9 Properties(OBDDs)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125005333920.png" alt="image-20230125005333920" style="zoom:67%;" />

6.9.1 OBDD Alg 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125005411632.png" alt="image-20230125005411632" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125005443177.png" alt="image-20230125005443177" style="zoom:67%;" />

**Example**



<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125010311840.png" alt="image-20230125010311840" style="zoom:67%;" />

#### 6.9 Applying Boolean functions OBDDs

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125012045086.png" alt="image-20230125012045086" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125012117878.png" alt="image-20230125012117878" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125012210387.png" alt="image-20230125012210387" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125012309636.png" alt="image-20230125012309636" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125012406946.png" alt="image-20230125012406946" style="zoom:67%;" />

### 7.QBF 

#### 7.1 Two-Player Games



<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125122433158.png" alt="image-20230125122433158"  />

![image-20230125122620095](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125122620095.png)

#### 7.2 QBF  

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125122734559.png" alt="image-20230125122734559"  />

##### 7.2.1 Quantifiers

![image-20230125141155464](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125141155464.png)

##### 7.2.2 New Notation 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125141249534.png" alt="image-20230125141249534" style="zoom:80%;" />

##### 7.2.3 QBF Sementics 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125141411479.png" alt="image-20230125141411479" style="zoom:80%;" />

#### 7.3 Evaluating a formula : and or tree 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125141522328.png" alt="image-20230125141522328" style="zoom:80%;" />

**Evaluating a formula**

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125141742074.png" alt="image-20230125141742074" style="zoom:80%;" />

#### 7.4 QBF: positions, polarity, free and bound variables

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125142052541.png" alt="image-20230125142052541" style="zoom:80%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125142147817.png" alt="image-20230125142147817" style="zoom:80%;" />

####     7.5 Free and bound occurrences of variables

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125142322342.png" alt="image-20230125142322342" style="zoom:80%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125142357537.png" alt="image-20230125142357537" style="zoom:80%;" />

 有 quantified 的叫做 bound  没有的叫做 free 

 没有free variable 的叫做 Closed formula 

 没有 bound 的叫做 free occurence 

##### 7.5.1 Only Free Variables Matter

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125142703174.png" alt="image-20230125142703174" style="zoom:80%;" />

#### 7.6 Truth, Validity , Satifiability 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125142629256.png" alt="image-20230125142629256" style="zoom:67%;" />

#### ·7.7 QBF: substitutions, rectification

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125143103755.png" alt="image-20230125143103755" style="zoom:80%;" />

 											<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125143158392.png" alt="image-20230125143158392" style="zoom:80%;" />	

#### 7.8 Renaming bound var 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125143251162.png" alt="image-20230125143251162" style="zoom:80%;" />

##### 7.8.1 Rectified formulas  

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125143612037.png" alt="image-20230125143612037" style="zoom:80%;" />

##### 7.8.2 Variable capture

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125145643901.png" alt="image-20230125145643901" style="zoom:67%;" />

##### 7.8.3 Jointly rectified formulas

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125150127540.png" alt="image-20230125150127540" style="zoom:67%;" />

##### 7.8.4 Rectification assumption

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125151120404.png" alt="image-20230125151120404" style="zoom:80%;" />

#### 7.9 Prenex form

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125151330918.png" alt="image-20230125151330918" style="zoom:67%;" />

​                      

##### 7.9.1 Prenexing rules

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125151511901.png" alt="image-20230125151511901" style="zoom:80%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125153202510.png" alt="image-20230125153202510" style="zoom:67%;" />





### 8.QBF(part2)

#### 8.3 QBF(CNF) <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125173832900.png" alt="image-20230125173832900" style="zoom:80%;" />

#### 8.4 QBF: CNF transformation

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125174100454.png" alt="image-20230125174100454" style="zoom:80%;" />

8.5  QBF(DPLL)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125174134344.png" alt="image-20230125174134344" style="zoom:80%;" />

8.6 QBF-DPLL(Alg)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125174301733.png" alt="image-20230125174301733" style="zoom:67%;" />



<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125175023923.png" alt="image-20230125175023923" style="zoom:80%;" />

#### 8.5 QBF: DPLL optimisations 

##### 8.5.1  Pure literal rule 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125210401094.png" alt="image-20230125210401094" style="zoom:80%;" />

##### 8.5.2 Universal literal deletion 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125211630023.png" alt="image-20230125211630023" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125213015371.png" alt="image-20230125213015371" style="zoom: 80%;" />

#### 8.6 QBF: using OBDDs for representing QBFs

##### 8.6.1 Quentification

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125213211082.png" alt="image-20230125213211082" style="zoom:67%;" />

##### 8.6.2 Quantification for Obdds(Alg)

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125213254784.png" alt="image-20230125213254784" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125214022750.png" alt="image-20230125214022750" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125214045989.png" alt="image-20230125214045989" style="zoom:67%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125214107100.png" alt="image-20230125214107100" style="zoom:67%;" />

##### 8.6.3 Quantifier elimination

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230125214159253.png" alt="image-20230125214159253" style="zoom:67%;" />

### 9.PLFD

