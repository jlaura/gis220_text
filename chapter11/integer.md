# Integer Programming

One of the properties of the linear programming is that it is continuous, such that decision variables are allowed to be fractional. Although this is a realistic assumption, sometimes we cannot allow such fractional decisions. For example, consider that we want to decide location of tornado warning sirens. We have a set of candidate sites for the sirens. If we have $$n$$ candidate sites, decision variable ($$x$$) is whether a siren is location at site $$x_{j} (j = 1,2,\ldots, n)$$ or not. If we locate a siren, then $$x = 1$$, or if not, $$x = 0$$. It is not possible to make them 0.5 or 2.1. In this kind of problem, decision variables need to be go-or-no-go kind, or binary type. Another example is that problem of scheduling airline crews. You cannot schedule 0.6 people. In this case, decision variables also should be integer.

Followings are examples of integer programming.

## Knapsack Problem

I want to pack a suitcase for a conference in Washington D.C. and need to bring many things. However, due to weight limitations for luggage of the airline, he cannot carry all desired items. So naturally I try to maximize value (or usage, benefits) of things to bring while satisfying the weight restriction.

Here are assumptions of this problem:
- Each object has a positive weights and value: it may sound silly (negatively weighted things?), but such things should be explicitly stated.
- The objects are independent from each other.
- The suitcase can carry way combination of given objects.
Objective of this problem is maximizing the value of things in the suitcase.

Before we start, we need to define notations:

* n: the number of objects
* j: index of object $$j = (1,2,3,\ldots,n)$$
* $$w_{j}$$: the weight of object $$j$$
* $$v_{j}$$: the value of object $$j$$
* b: the maximum weight restriction

Decision variable is:

* $$x_{j} = 1$$ if the object is selected, otherwise 0

The objective is maximizing the value of things in the suitcase:

<center>$$max \sum_{j=1}^{n}v_{j}w_{j}$$ (1)</center>

*s.t.*

<center>$$\sum_{j=1}^{n}w_{j}x_{j} \leq b$$ (2)<\center>
<center>$$x_{j} = 0 or 1$$</center>

The objective function (1) tries to maximize the value of objects to be carried in the suitcase. Constraint (2) restricts the total weight of selected object for the conference should be less than or equal to the given weight restriction. Constraint (3) is called binary restriction, and it makes this problem binary integer problem.
