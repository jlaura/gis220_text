# Combinations

Now suppose that you were not concerned with the way the pieces of candy were chosen but only in the final choices. In other words, how many different combinations of two pieces could you end up with? In counting combinations, choosing red and then yellow is the same as choosing yellow and then red because in both cases you end up with one red piece and one yellow piece. Unlike permutations, order does not count. Table 3 is based on Table 2 but is modified so that repeated combinations are given an "x" instead of a number. For example, "yellow then red" has an "x" because the combination of red and yellow was already included as choice number 1. As you can see, there are six combinations of the three colors.

|Number|	First	|Second|
|------|---------|------|
|1|	red|	yellow
|2|	red	|green
|3|	red	|brown
|x|	yellow	|red
|4|	yellow	|green
|5|	yellow|	brown
|x|	green|	red
|x|	green|	yellow
|6|	green|	brown
|x|	brown|	red
|x|	brown|	yellow
|x|	brown|	green

The formula for the number of combinations is shown below where nCr is the number of combinations for n things taken r at a time.

$$_{n}C_{r} = \dfrac{n!}{(n-r)!r!}$$

For out example, 

$$ _{4}C_{2} = \dfrac{4!}{(4-2)!2!} = \dfrac{4 \cdot 3 \cdot 2 \cdot 1}{(2 \cdot 1)(2 \cdot 1)} = 6$$

which is consistent with Table 3.

As an example application, suppose there were six kinds of toppings that one could order for a pizza. How many combinations of exactly 3 toppings could be ordered? Here n = 6 since there are 6 toppings and r = 3 since we are taking 3 at a time. The formula is then:

$$_{6}C_{3} = \dfrac{6!}{(6-3)!3!} = 20$$

#### Supplemental Video

[![Combinations](http://img.youtube.com/vi/iKy-d5_erhI/0.jpg)](https://www.khanacademy.org/math/precalculus/prob-comb/combinations/v/introduction-to-combinations)