# Basics of Spatial Optimization (Model Formulation) 

## Model Building Fundamentals

Frequently, optimization problems are given in verbal description. To get the optimal answer, or at least determine if the given problem has feasible solution(s) or not, we need to describe the problem in quantitative, mathematical expressions.
An optimization model has three basic components:

* Objective function: mathematical expression of objective of given problem. It can be maximization or minimization of a linear function.
* Decision variables: unknown variables that need to be determined to achieve objective.
* Constraints: given conditions need to be satisfied.

## Example: Apple Shipping Problem

> An apple orchard try to determine the amount of apples to be shipped to three customers, Taylor, Shuyao, and Nazli. The goal is to minimize shipping cost while satisfying requirements of the customers and other conditions.> The orchard have 12 tons of apples to sell. Taylor wants 3 tons of apples, but he can use up to 12 tons if possible. Shuyao needs as many as apples he can get from the orchard. Nazli wants at least 1 ton of apples, but does not want more than 2 tons. This orchard has a strange set of rules based on past commitments to three customers. The orchard will supply Shuyao with two times that given to Taylor. Also, the orchard will ship Nazli only one third that of Taylor. Finally, shipping cost to each customer like following: 11/ton for Taylor, 4/ton for Shuyao, and 20/ton for Nazli, based on shipping distance to each.

First, we must define decision variables. In this case, decision variables will be amount of apples that will be shipped to each customer.

$$T$$ = tons of apples supplied to Taylor 
$$A$$ = tons of applies supplied to Shuyao 
$$N$$ = tons of applies supplied to Nazli

So we have three decision variables.
Second, what is the objective of this problem? Minimizing the transportation cost, and transportation cost varies for each customer. So we can say:

Minimize: $$11T + 4S + 20N$$

Finally, we need to translate these given conditions, constraints in modeling term, to mathematical expressions. In case of the orchard, it has limitation on available supply of apples. As we already defined the decision variables, this supply constraint should be expressed in terms of the decision variables

$$T + H + N \leq 12$$

Taylor has two conditions (constraints): $$T \geq 3$$ and $$T \leq 12$$.

In case of Shuyao, he does not have any constraint in terms of amount of apples, as he just wants as many as he can get.For Nazli, $$N \geq 1$$ and $$N \leq 2$$.

We can mathematically express the 'strange set of rules' as:

$$2T -S = 0$$

$$3N - T = 0$$

Therefore, the fully formulated optimization problem is:
<p style="text-align: center;">
Minimize: $$11T + 4S + 20N$$
</p>
Subject to:
<p style="text-align: center;">
$$T + H + N \leq 12$$
<p style="text-align: center;">
$$T \geq 3$$
<p style="text-align: center;">
$$T \leq 12$$
<p style="text-align: center;">
$$N \geq 1$$
<p style="text-align: center;">
$$N \leq 2$$
<p style="text-align: center;">
$$2T -S = 0$$
<p style="text-align: center;">
$$3N - T = 0$$
<p style="text-align: center;">
$$ T, H, N \geq 0$$
<\p>

What’s the last constraint? It is nonnegativity conditions, because it does not make any sense if we ship any negative amount of apples. If you forget put it, the result of optimization possibly contains negative amount of apples (apples made of antimatter? It sounds dangerous).
