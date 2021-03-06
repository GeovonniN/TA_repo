##Week6.2

        Assigned problem file name:
        +---------+------------+---------------------------------------------------+
        | set_id  | problem_id | source_file                                       |
        +---------+------------+---------------------------------------------------+
        | Week6.2 |          1 | Reorganized/ExponentialPoisson/poisson_zz.pg      |
        | Week6.2 |          2 | Reorganized/ExponentialPoisson/ur_pb_14_1.pg      |
        | Week6.2 |          3 | Reorganized/ExponentialPoisson/ur_pb_9_4.pg       |
        | Week6.2 |          4 | Reorganized/ExponentialPoisson/stat212-HW06-20.pg |
        | Week6.2 |          5 | Reorganized/ExponentialPoisson/poisson_rs.pg      |
        | Week6.2 |          6 | Reorganized/ExpectationVariance/probs69.pg        |
        | Week6.2 |          7 | Reorganized/ExpectationVariance/ExpVarOfSum.pg    |
        | Week6.2 |          8 | Reorganized/CentralLimitTheorem/ur_pb_12_4.pg     |
        | Week6.2 |          9 | Reorganized/CentralLimitTheorem/ur_pb_11_7.pg     |
        | Week6.2 |         10 | Reorganized/CentralLimitTheorem/ur_pb_12_3.pg     |
        | Week6.2 |         11 | Reorganized/CentralLimitTheorem/clt_demo.pg       |
        +---------+------------+---------------------------------------------------+


### Sorted with number of attempts
[problem 9](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_9_clusters.md): 2205

		 part  1 :  64
		 part  2 :  372
		 part  3 :  57
		 part  4 :  696
		 part  5 :  191
		 part  6 :  379
		 part  7 :  446


[problem 10](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_10_clusters.md): 2001

		 part  1 :  146
		 part  2 :  462
		 part  3 :  1393


[problem 8](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_8_clusters.md): 1838

		 part  1 :  216
		 part  2 :  352
		 part  3 :  593
		 part  4 :  253
		 part  5 :  424


[problem 6](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_6_clusters.md): 1754

		 part  1 :  111
		 part  2 :  290
		 part  3 :  137
		 part  4 :  304
		 part  5 :  50
		 part  6 :  462
		 part  7 :  46
		 part  8 :  354


[problem 11](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_11_clusters.md): 1661

		 part  1 :  331
		 part  2 :  742
		 part  3 :  221
		 part  4 :  367


[problem 5](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_5_clusters.md): 1483

		 part  1 :  108
		 part  2 :  1075
		 part  3 :  300


[problem 1](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_1_clusters.md): 1344

		 part  1 :  601
		 part  2 :  293
		 part  3 :  450


problem 2 (Problem changes acording to randome seed): 1236

		 part  1 :  369
		 part  2 :  867


[problem 7](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_7_clusters.md): 1024

		 part  1 :  309
		 part  2 :  105
		 part  3 :  75
		 part  4 :  157
		 part  5 :  82
		 part  6 :  296


[problem 4](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_4_clusters.md): 984

		 part  1 :  984


[problem 3](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week6.2/md_files/Week6.2_3_clusters.md): 487

		 part  1 :  487



### Problem Content

Problem 1

    $x = random(8,10,1);
    $X = $x*$x;
    $y = random(0,5,1);
    $lambda = 400/($X);

    You will be using Poisson Distribution in this problem. Review: a discrete random variable [`X`] is said to have a Poisson distribution with parameter [`\lambda > 0`], if for k = 0, 1, 2, ... the probability mass function of [`X`]  is given by:

    [`\Pr(X=k) = e^{-\lambda} \frac{\lambda^k}{k!}`]

    Assume that you live in a district of size [`[$x]`] blocks by [`[$x]`] blocks so that the total district is divided into [`[$X]`] small squares. How likely is it that the square in which you live will receive [`[$y]`] hits if the total area is hit by [`400`] bombs. Assume the probability that a particular bomb will hit your square with probability [`1/[$X]`].

    o What is [`\lambda`] in the Poisson Distribution? [__________]{Compute("400/$X")}

    o Using Poisson Distribution, what is the approximate probability that your square will receive [`[$y]`] hits? [________________]{Compute("e^(-$lambda)*$lambda^$y/($y!)")}

    o What is the expected number of squares that will receive exactly [`[$y]`] hits using the approximate probability from above? [________________]{Compute("($x*$x)*(e^(-$lambda)*$lambda^$y/($y!))")}


Problem 2

	(Doesn't work on attempts grouping because the problem changes accordingly)
	
    $lambda = random(.1, .9, .1);
    $k = random(3,10,1);
    @q = ( "the probability that a repair time exceeds $k hours?", "the probability that a repair takes less than $k hours?");
    @a = (Compute("e**(-$lambda*$k)"), Compute("1-e**(-$lambda*$k)"));
    $i = list_random(0..1);
    $qq=$q[$i];
    $ans1 = $a[$i];

    $m = random(3,9,1);
    $n = $m + random(1,5,1);
    $ans2 = Compute("e**($lambda*($m-$n))");

    Suppose that the time (in hours) required to repair a machine is an exponentially distributed random variable with
    parameter [`\lambda = [$lambda]`]. What is

    (a)  [$qq]* [____________]{$ans1}

    (b) the conditional probability that a repair takes at least [$n] hours, given that it takes more than [$m] hours? [_____________]{$ans2}



Problem 3

    $a = random(1,5,0.1);
    $b = random(1,5,0.1);
    while ( abs($a - $b) < 0.5 ) { $b = random(1,5,0.1); }

    $ans = Compute("(e^(-$a) + e^(-$b))/2");

    BEGIN_PGML

    A certain typing agency employs two typists. The average number of errors per article is
    [$a] when typed by the first typist and [$b] when typed by the second.
    If your article is equally likely to be typed by either typist, find the probability
    that it will have no errors. [___________________]{$ans->with(tolType=>'absolute', tolerance=>'0.01')}



Problem 4

    $ans1 = 0;
    while ($ans1 < 0.002) {
    $mu = random(5,7,.5);
    $lambda = 1/$mu;
    $a = random(9,12,1);
    $x = $lambda*$a;
    $ans1 = Compute("e^(-$x)");
    }

    The manager of a supermarket tracked the amount of time needed
    for customers to be served by the cashier.  After checking with
    his statistics professor, he concluded that the checkout times
    are exponentially distributed with a mean of [$mu] minutes.  What
    propotion of customers require more than [$a] minutes to check out?

    Proportion = [____________]{$ans1}




Problem 5

    $k = random(1,2,1);
    $r = random(1,2,1);
    $a = random(800,1200,100);
    $select = random(8,15,1);
    $s = $a/10;

    $j = random(1,3,1);

    $x = random(12,15,1);
    $y = random(5,6,1);

    $a1 = Compute("C($x-2*$y+$y-1,$x-2*$y)");
    $a2 = Compute("C($x-3+($y-2), $y-2)");

    #### The Poisson Distribution

    There is a typesetter who, on average, makes one mistake per [$a] words. Assume that he is setting a book with [$s] words to a page.  Let [`S_{[$s]}`] be the number
    of mistakes that he makes on a single page.

    o What is the expected value of [`S_{[$s]}`]? [_____]{$s*1/$a}

    o What is the exact probability that [`S_{[$s]}`] = [$j]? [_______]{ Compute(" C($s,$j)* ( (1/$a)^$j) * ( (1-1/$a)^($s-$j) ) ")->with(tolType=>'absolute', tolerance=>'0.000001') }

    o What is the Poisson approximation of [`S_{[$s]}`] = [$j]? [_______]{ Compute(" e^(-.1)*(.1)^$j/$j! ") }




Problem 6

    $n = 2*random(40,50,1);

    Let [`X_1, X_2, \ldots, X_{100}`] be the outcomes of [`100`] independent rolls of a fair coin.
    [`P(X_i=0)=P(X_i=1)=0.5`]

    1. [`\mathbb{E}(X_1) = `][____]{"1/2"}
    2. [`var(X_1) = `][_______]{"1/4"}

    Define the random variable [`X`] to be [`X_1 - X_2`].
    3. [`\mathbb{E}(X) = `][______]{"0"}
    4. [`var(X) = `][_______]{"1/2"}
       *Hint:* if [`X,Y`] are independent random variables then [`var(X+Y)=var(X)+var(Y)`]

    Define the random variable [`Y = X_1 - 2X_2 + X_3`].
    5. [`\mathbb{E}(Y) = `][_______]{"0"}
    6. [`var(Y) = `][_________]{"6/4"}
       *Hint:* if [`a`] is a constant and [`X`] a random variable, then [`var(aX)=a^2 var(X)`].

    Define the random variable [`Z = X_1 - X_2 + X_3 - X_4 + ... + X_{[$n-1]} - X_{[$n]}`].
    7. [`\mathbb{E}(Z) = `][_______]{"0"}
    8. [`var(Z) = `][_________]{"$n/4"}




Problem 7

    $a = random(1,5);
    $b = random(6,10);

    ## The mean, or expected value  ##

    ---
    Let [`X_1, X_2, \cdots X_{5}`]  be independent random variables with:
    [$BCENTER]*
    [``\mathbb{E}(X_i) = \frac{[$a]}{i} \hspace{10pt} \mbox{VAR}(X_i) = \frac{[$b]}{i^2}``]
    [$ECENTER]*
    ---
    Compute:

    * the mean of [`X_1 + X_2 + X_3 + X_4 + X_5`] [_____________________________]{Compute("$a*(1+1/2+1/3+1/4+1/5)")}
    * ...and the variance [______________________________]{Compute("$b*(1+1/4+1/9+1/16+1/25)")}

    * the mean of [`X_1 - X_2 + X_3 - X_4 + X_5`] [_______________________________]{Compute("$a*(1-1/2+1/3-1/4+1/5)")}
    * ...and the variance  [________________________________]{Compute("$b*(1+1/4+1/9+1/16+1/25)")}


    * the mean of [`X_1 - 2X_2 + X_3 - 2X_4 + X_5`] [_______________________________]{Compute("$a*(1-2/2+1/3-2/4+1/5)")}
    * ...and the variance [________________________________]{Compute("$b*(1+1/9+1/25) +$b*4*(1/4+1/16)")}




Problem 8

    $n = random(20,30,1);
    $nc = random(4,6,1);
    $p = 1/$nc;
    $mean = $n*$p;
    $low = int($mean + 4);
    $high = int($mean + 8);
    $corr = random($low, $high, 1);

    $std = sqrt( $n / $nc * (1-1/ $nc));
    $ans = Compute("Q(($corr-$mean)/$std)");
    $ans1 = BinomDistTail($n,$p,$corr);

    ### Some Definitions ###
    The *standard* normal distribution [`\mathcal{N}(0,1)`] is a special normal distribution with mean [`\mu=0`] and standard deviation [`\sigma=1`].

    - The CDF of the standard normal distribution is denoted [`\Phi`]:
    >>[``\Phi(z) = P(Z\leq z)``]. <<

    - The complement of the CDF is called the *Q-function*:
    >>[``Q(z) = P(Z>z) = 1-\Phi(z)``].<<

    While [`\Phi(z)`] measures the probability mass of a "head" of the standard normal, [`Q(z)`] measures the "tail". The values of Q are often tabulated for commonly used \(z\). One such table is _http://goo.gl/Szofn1_. One can also use _http://wolframalpha.com_ to find numeric values for Q function.


    - An alternative representation of the head probability is the *error function*, denoted [`erf`]. It is related to [`\Phi`] by:
    >>[``\Phi(x) = \frac{1}{2} + \frac{1}{2}erf(\frac{x}{\sqrt{2}})``]<<

    *For this set of assignment, you can use "Phi", "Q" or "erf" as functions in your answer.*

    ---

    ### Recap for Binomial Distribution ###

    Suppose a monkey is given a test that consists of [$n] multiple-choice questions each with [$nc] choices. By random guessing, what is the *exact* probability that the monkey gets at least [$corr] correct ?
    [_____________________________________________________________]{$ans1}

    ---
    ### Approximate Binomial Using Normal Distribution ###
    We know that the number of questions the monkey guesses correctly follows a binomial distribution, and we have computed the *exact* probability of a tail of this distribution, by summing up all cases in the tail.

    Now, we assume the number of questions is large enough so that by *central limit theorem* we can use a normal distribution to approximate the binomial distribution. This makes computing the probability of a certain part of the distribution much easier.

    ---
    Again, suppose the monkey is taking a multiple-choice test that consists of [$n] questions each with [$nc] possible answers, let us estimate the probability that it gets at least [$corr] questions correct, this time using an *approximated normal distribution*.

    Suppose [`X`] is the number of correct answers.

    - What is the mean of [`X`] ? [_______]{Compute("$n*$p")}
    - What is the standard deviation of [`X`] ? [_______]{Compute("sqrt($n*$p*(1-$p))")}
    - What is the z-score of [`X=[$corr]`]? [___________]{Compute("($corr-$mean)/$std")}
    - What is the estimated probability that [`X \ge [$corr]`] ? [_____________]{$ans}





Problem 9

    $n = random(40,100,5);
    $d = random(2,5,1);

    $dev = 1/sqrt(12)*sqrt($n);
    $a1 = Compute("Q($d/$dev)");
    $ans = Compute("2*Q($d/$dev)");

    [$n] numbers are rounded off to the nearest integer and then summed. Suppose the individual round-off error are uniformly distributed over [` (-.5, .5) `].

    ---
    Remember a random variable that follows a uniform distribution over [`(a,b)`] has a mean of [`(a+b)/2`], and variance of [`\frac{1}{12}(b-a)^2`].

    What is the mean of the round-off error of one number? [_____________]{0}

    What is the standard deviation of the round-off error of one number? [_____________]{"sqrt(1/12)"}

    ---
    Suppose the *sum* of the round-off errors is [`Y`].

    What is the mean of [`Y`]? [_____________]{0}

    What is the standard deviation of [`Y`]? [_____________]{"1/sqrt(12)*sqrt($n)"}

    ---
    To compute the probability that the resultant sum of the [$n] numbers differs from the exact sum by more than [$d], we find the two tails on the distribution of [`Y`].

    What is the z-score at [`Y=[$d]`] ? [__________]{"($d-0)/$dev"}.

    What is the probability that the rounded sum is *larger* than the exact sum by more than [$d] ?[____________]{$a1}

    What is the probability that the rounded sum *differs* from the exact sum by more than [$d] ?[____________]{$ans}




Problem 10

    $b = random(150,400,1);
    $p = random(0.8,0.9,0.01);
    $mean =$b*$p;
    $dev = sqrt ($b * $p * (1 - $p));

    $z = random(1.7, 3.1, 0.01);
    $s = 10*int(($z * $dev + $mean)/10+1);

    $ans = Compute("Q(($s-$mean)/$dev)");

    An airline company is considering a new policy of booking as many as [$b] persons on an
    airplane that can seat only [$s].
    (Past studies have revealed that only [$p*100]% of the booked passengers actually arrive for the flight.)

    What is the mean of the number of passengers that arrive for the flight ? [________]{$mean}

    What is the standard deviation ? [________]{$dev}

    Estimate the probability that if the company books [$b] persons, not enough seats will be
    available. [__________]{$ans}




Problem 11

    $a = random(-3,-1,1);
    $b = $a + random(2,6,1);
    $lambda = random(0.1, 0.9, 0.1);

    $n1 = random(100,500,10);
    $n2 = random(100,500,10);

    ### CLT simulation

    In this problem, you may use the CLT simulation
    (http://webwork.cse.ucsd.edu/misc/clt.html) to help you find the
    answers.

    ---

    Suppose a sample average is denoted by [`S_n = (\sum_{i=1}^n X_i) /
    n`] and we define [`T_n = (S_n - A) / B`].

    Find the values of [`A`]
    and [`B`] under the following conditions so that [`T_n`] is
    distributed normally with [`\mu = 0`] and [`\sigma = 1`]. Your answers should be correct up to 2 decimal points.

    o  [`X_i \sim \mbox{Uniform}([$a],[$b])`] and [`n = [$n1]`]
        -  A = [________]{Compute("($a+$b)/2")->with(tolType=>'absolute', tolerance=>'0.01')}
        -  B = [________]{Compute("sqrt((($b-$a)**2/12) / $n1)")->with(tolType=>'absolute', tolerance=>'0.01')}

    o  [`X_i \sim \mbox{Exponential}([$lambda])`] and [`n = [$n2]`]
        -  A = [________]{Compute("1/$lambda")->with(tolType=>'absolute', tolerance=>'0.01')}
        -  B = [________]{Compute("sqrt((1/$lambda**2) / $n2)")->with(tolType=>'absolute', tolerance=>'0.01')}
