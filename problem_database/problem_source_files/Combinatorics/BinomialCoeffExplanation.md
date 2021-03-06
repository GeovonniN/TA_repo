```python
from math import sqrt
from math import exp
from math import factorial as f

def cnk(n, k):
    return int(f(n)/f(k)/f(n-k))

def pmt(n, k):
    return int(f(n)/f(n-k))
Tk = [1,2,3,2,5,7,9]
Tn = [3,3,3,10,10,10,10]
t = random.randrange(0,7,1)
n = Tn[t]
k = Tk[t]

R1=random.randrange(5,20,1)  # Number of balls (both white and black)
R2=random.randrange(2,R1-1,1)  # Number of white balls

solution1 = "{0}!/({1}!*({0}-{1})!)".format(R1,R2)

solutions = [solution1]
```

Snow White is off to pick strawberries and asks three of the dwarfs chosen
from the set of size seven: \\\(\\\{Dopey, Grumpy, Doc, Happy, Bashful, Sneezy, Sleepy\\\}\\\) to join
her. How many possible groups are there?

In this case, it is misleading to represent an outcome as a 3-tuple,
because, for instance, \\\((Dopey, Sleepy, Doc)\\\) is a different
3-tuple from \\\((Sleepy, Dopey, Doc)\\\) but they represent the
same group. So if we count tuples, we would be
*over-counting*. Instead, we ought to represent an outcome as a set,
\\\(\\\{Dopey, Doc, Sleepy\\\}\\\)

So the question becomes: how many different subsets of three dwarfs are there?
In general, a set of size \\\(n\\\) has

(A) \\\[{n \choose k} \ \doteq \ \frac{n!}{k! (n-k)!}\\\]

subsets of size \\\(k\\\).  So in our example, the answer is \\\({7 \choose 3} = 35\\\). Formula (A) is called the *Binomial formula* or the *Binomial coefficient*.

Let's step back and derive Formula (A): how many subsets of size \\\(k\\\)
does a set of \\\(n\\\) elements have? We will use the following
strategy. First, we will assume that the order of the elements in the
set *does* matter. Then we will calculate the amount by which we
over-counted and divide the first result by it.

* How many sequences of length \\\(k\\\) (where order does matter) can
 we choose from a set of \\\(n\\\) different elements? We already have
 the formula for this from the analysis of "sampling without
 replacement when the order matters" (remember the children choosing
 the dogs example...). So you surely remember that the formula is

(B)  \\\[  \frac{n!}{(n-k)!} \\\]

* Ok, so now we have the number of sequences of length \\\(k\\\), but we
 want to count sets not sequences, in other words, order does
 not matter. By counting all sequences we have counted each set a
 number of times. Convince yourself that this number is the same for
 all sets of size \\\(k\\\). If we can calculate this number, we can
 divide formula (B) by it and get the correct number of sets. So,
 how many ways are there to order \\\(k\\\) elements? (hint, recall
 computing the number of ways to shuffle a deck of cards) it is:

(C) \\\[k! \\\]

* Dividing (B) by (C) we get the Binomial Equation:

(A) \\\[{n \choose k} \ \doteq \ \frac{n!}{k! (n-k)!} \\\]

EXAMPLE:

Binomials appear everywhere. here is another example: how many strings in \\\(\\\{0,1\\\}^{10}\\\) contain exactly
four 1s?  Well, we need to choose four positions of the ten
possibilities in which to place the 1s; that is, we choose a subset of
size four from \\\(\\\{1,2,\ldots,10\\\}\\\)   The number of ways to do this is \\\({10 \choose 4} = 210\\\)

PROBLEM:

Suppose we have $R1 bins, numbered 1,...,$R1 and that we have $R1 balls,
$R2 of them white and $R1-$R2 of them black.

o How many white/black patterns can one make by placing the balls in the bins?

[_]
