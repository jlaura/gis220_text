# Introduction

> *What is computational geometry?* Computational geometry is a term claimed by a number of different groups. The term was coined perhaps first by Marvin Minsky in his book “Perceptrons”, which was about pattern recognition, and it has also been used often to describe algorithms for manipulating curves and surfaces in solid modeling. Its most widely recognized use, however, is to describe the subfield of algorithm theory that involves the design and analysis of efficient algorithms for problems involving geometric input and output.
> 
>

Given that definition, an immediate response might be to ask what any of that has to do with GISystems or GIScience.  If I were to rewrite David's definition from the perspective of a GIScientist, I would be inclined to focus on what I see as the primary goal of computational geometry.  That is, research and development development of (the most) efficient algorithms to solve discrete geometric problems in low dimenstionality space.  These algorithms support operations that geographers frequently apply in GISystems such as line segment intersection (find me all of the streets that intersect with Mill), convex hulls (what is the smallest study area that includes all of the bird nests someone is interested in studying), Voronoi diagrams (how can we partition the urban space to support improved interaction between different units?), Delaunay triangulation ( for the generation of a TIN elevation model from point observations), and rectangular range search (how can we efficienlty perform spatial queries?).

### Efficiency

Computational geometry focuses heavily on the concept of *efficiency*.  This characteristic naturally falls out of the drive to identify the optimal (best possible) way to solve a given problem.  The fewer, less complex steps that can be applied to solve a problem, the more efficient the algorithm is judged.  The more efficient the algorithm, the larger the possible range of computable inputs.  By way of example, point pattern analysis problems of the 1980s were often contrained to, at most, hundreds of observations, because of the computational cost to compute the necessary distance and permutation metrics.  Fast-forward to today, and we can process point data sets hundreds of times larger.  The ability to process larger data sets is not just because of the improvement in computers, but also because of the improvements in the underlying algorithms!

### Algorithms

The mathematics of computational geometry also differs from the previous chapters in that we are now looking at discrete algorithmic mathematics.  Soicher and Vivaldi (2004) informally define an algorithm as 'a finite sequence of unambiguous instructions to perform a specific task'.

For example, I could write an algorithm: 'Draw a card from a deck of cards.  If the card is red, add one to $$x$$.  Then discard the card and draw another one.'  Here we have a discrete set of unambiguous instructions to perform some task.  For a more complex example, that is more true to what you might encounter, take a look at [Route Finding](https://www.khanacademy.org/computing/computer-science/algorithms/intro-to-algorithms/a/route-finding).

#### Supplemental Video

[![Algorithms](http://img.youtube.com/vi/CvSOaYi89B4/0.jpg)](https://www.khanacademy.org/computing/computer-science/algorithms/intro-to-algorithms/v/what-are-algorithms)

### Computational Thinking
Expressing simple ideas, such as 'count to 26 by only counting red cards in a standard playing card deck' might sound absurd.  While the example is contrived, the underlying skills that are required to reformulate the problem so that a computer (or human) can maximize efficiency for completion are critical.  In fact, computational thinking (along with spatial thinking) are two skills that are invaluable in the job market!  Skim this [computational thinking PDF](http://www.ctillustrated.com/wp-content/uploads/2011/10/computational-thinking-illustrated.pdf).

[^1]: Copyright, David M. Mount, 2002, Dept. of Computer Science, University of Maryland, College Park, MD, 20742. These lecture notes were prepared by David Mount for the course CMSC 754, Computational Geometry, at the University of Maryland. Permission to use, copy, modify, and distribute these notes for educational purposes and without fee is hereby granted, provided that this copyright notice appear in all copies.