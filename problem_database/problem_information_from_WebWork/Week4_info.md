##Week4

        Assigned problem file name:
        +--------+------------+------------------------------------------------------------------------------+
        | set_id | problem_id | source_file                                                                  |
        +--------+------------+------------------------------------------------------------------------------+
        | Week4  |          1 | Reorganized/CumulativeDistributionFunctions/cdf_rs.pg                        |
        | Week4  |          2 | Reorganized/CumulativeDistributionFunctions/cumulative_uniform_masses_5.pg   |
        | Week4  |          3 | local/Reorganized/CumulativeDistributionFunctions/cdf_random.YoavsVersion.pg |
        | Week4  |          4 | Reorganized/BayesConditional/BayesBurglary_ZZ.pg                             |
        | Week4  |          5 | Reorganized/BayesConditional/probs_43_with_randomization.pg                  |
        | Week4  |          6 | Reorganized/PokerConditional/poker_cond4_1.pg                                |
        | Week4  |          7 | Reorganized/PokerConditional/poker_cond5_1.pg                                |
        | Week4  |          8 | Reorganized/PokerConditional/poker_cond2_1.pg                                |
        | Week4  |          9 | Reorganized/PokerConditional/poker_cond3.pg                                  |
        | Week4  |         10 | Reorganized/PokerConditional/poker_cond6_2.pg                                |
        +--------+------------+------------------------------------------------------------------------------+



### Sorted with number of attempts
[problem 2](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_2_clusters.md): 3885

		 part  1 :  737
		 part  2 :  485
		 part  3 :  560
		 part  4 :  1476
		 part  5 :  59
		 part  6 :  178
		 part  7 :  68
		 part  8 :  156
		 part  9 :  47
		 part  10 :  119


problem 3 (Graphs Problem): 2589

		 part  1 :  1555
		 part  2 :  356
		 part  3 :  282
		 part  4 :  339
		 part  5 :  57


[problem 7](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_7_clusters.md): 2166

		 part  1 :  1520
		 part  2 :  431
		 part  3 :  215


[problem 8](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_8_clusters.md): 1828

		 part  1 :  472
		 part  2 :  1143
		 part  3 :  69
		 part  4 :  144


[problem 10](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_10_clusters.md): 1401

		 part  1 :  616
		 part  2 :  173
		 part  3 :  497
		 part  4 :  115


[problem 6](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_6_clusters.md): 1349

		 part  1 :  611
		 part  2 :  738


[problem 1](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_1_clusters.md): 1282

		 part  1 :  830
		 part  2 :  452


[problem 4](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_4_clusters.md): 1132

		 part  1 :  83
		 part  2 :  159
		 part  3 :  396
		 part  4 :  494


[problem 9](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_9_clusters.md): 841

		 part  1 :  409
		 part  2 :  432


[problem 5](https://github.com/cse103/Attempt_Analysis/blob/master/clustering_code/clusters/Week4/md_files/Week4_5_clusters.md): 306

		 part  1 :  306



### Problem Content

Problem 1

    $n = random(20, 25, 1);
    $a1 = Compute("C($k+3,3)");
    $a2 = Compute("C($k+2,2)");
    $a3 = Compute("C($k-1+2,2)");
    $a4 = Compute("C($k-2+2,2)");

    ### Computing CDF
    Let [`X`] be a discrete random variable with the density function [`P(X=x) = x/z`], that is defined when [`x \in \{1, 2, ... , [$n]\}`], and [`z`] is a normalization constant. Let [`F`][`(X)`] be the CDF of [`X`].  What are the values of the following expressions?

    o [`F(5) = \frac{1}{z} (`][___________]{1+2+3+4+5}[`)`]

    o [`F([$n]) =  \frac{1}{z} (`][_______]{$n*($n+1)/2}[`)`]


Problem 2

    Given the following cumulative distribution:
    END_PGML
    BEGIN_TEXT
    $BR
    \{ image("cumulative_uniform_masses_5.png", width=>650, height=>500) \}
    END_TEXT
    BEGIN_PGML
    What are the uniform densities and mass distributions that could have been summed to produce this CDF?
    Uniform distributions:
    - Uniform on (0.00,[_____]{2.00}) of probability density [_____]{0.05}
    - Uniform on (1.00,[_____]{10.00}) of probability density [_____]{0.01}

    Point masses (ordered by the location):
    - Point mass at [_____]{1.00} with probability [______]{0.40}
    - Point mass at [_____]{7.00} with probability [______]{0.30}
    - Point mass at [_____]{12.00} with probability [______]{0.11}


Problem 3

	(Graph Problem)
    $rand_question = random(0,3,1);
    ######################################################################

    if ($rand_question == 0) {
    BEGIN_PGML
    Below is the CDF of a mixture distribution with *two* components.

    All parameters of component distributions are small multiples of 0.5.

    Component weights take on multiples of 0.05 and they need to sum to one.

    END_PGML
    BEGIN_TEXT
    $BR
    \{ image("mixture_cdf_1.png", width=>400, height=>320) \}
    END_TEXT
    BEGIN_PGML

    This distribution can be expressed as a mixture of two: a normal distribution and a point mass:
    [`p_1 N(\mu,\sigma) + p_2 PM(a)`]

    - The normal component [`N(\mu,\sigma)`] has parameters [`\mu=`][______]{-2.0}, and [`\sigma=0.5`]. Its component weight is
    [`p_1=`][_____]{0.5}
    - The point mass [`PM(a)`] is at location [`a=-0.5`]. Its component weight is [`p_2=`][_____]{0.5}
    END_PGML
    }

    if ($rand_question == 1) {
    BEGIN_PGML
    Below is the CDF of a mixture distribution with *two* components.

    All parameters of component distributions are small multiples of 0.5.

    Component weights take on multiples of 0.05 and they need to sum to one.

    END_PGML
    BEGIN_TEXT
    $BR
    \{ image("mixture_cdf_2.png", width=>400, height=>320) \}
    END_TEXT
    BEGIN_PGML

    This distribution can be expressed as a mixture of two: an exponential distribution and a uniform distribution
    [`p_1 Exp(\lambda) + p_2 U(a,b)`]

    Identify the component distributions:

    - The exponential component has [`\lambda`] of 0.5. Its component weight is [_____]{0.4}
    - Uniform component on the interval [`[a,b]=`] \[ [_______]{2.0},[_____]{3.5}  \]. Its component weight is [`p_2=0.6`]
    END_PGML
    }

    if ($rand_question == 2) {
    BEGIN_PGML
    Below is the CDF of a mixture distribution with *two* components.

    All parameters of component distributions are small multiples of 0.5.

    Component weights take on multiples of 0.05 and they need to sum to one.

    END_PGML
    BEGIN_TEXT
    $BR
    \{ image("mixture_cdf_18.png", width=>400, height=>320) \}
    END_TEXT
    BEGIN_PGML

    This distribution can be expressed as a mixture of two: an exponential distribution and a uniform distribution
    [`p_1 Exp(\lambda) + p_2 U(a,b)`]

    Identify the component distributions:

    - The exponential component has [`\lambda`] of 1.5. Its component weight is [`p_1=`][_____]{0.55}
    - Uniform component on the interval ([_______]{-4.5},[_____]{-2.0}). Its component weight is [`p_2=0.45`]
    END_PGML
    }

    if ($rand_question == 3) {
    BEGIN_PGML
    Below is the CDF of a mixture distribution with *two* components.

    All parameters of component distributions are small multiples of 0.5.

    Component weights take on multiples of 0.05 and they need to sum to one.

    END_PGML
    BEGIN_TEXT
    $BR
    \{ image("mixture_cdf_10.png", width=>400, height=>320) \}
    END_TEXT
    BEGIN_PGML

    This distribution can be expressed as a mixture of two: an exponential distribution and a point-mass distribution
    [`p_1 Exp(\lambda) + p_2 PM(a)`]

    Identify the component distributions:

    - The exponential component has [`\lambda=`] of 1.0. Its component weight is [`p_1=`][_____]{0.3}
    - Point mass on [`a=`][_______]{2.0}. Its component weight is [`p_2=`][_____]{0.7}
    END_PGML
    }



Problem 4

    $atpt = random(92,96,1);#false burglary percentage
    $perc = $atpt/100;
    $fals = random(1,3,1);#burglary percentage
    $fperc = $fals/100;
    $sol = Compute("($perc/10000)/($perc*0.0001+ $fperc*0.9999)");

    BEGIN_PGML
    ## Bayes' Burglary ##
    The following example is taken from _Probabilistic Reasoning in Intelligent Systems_ by Judea Pearl:
    '''You wake up in the middle of the night to the shrill sound of your burglar alarm. What is the chance that a burglary attempt has taken place?'''
    The relevant facts are:
    o  There is a [$atpt]% chance that an attempted burglary attempt will trigger the alarm. That is,
    [`` P(\mbox{alarm} | \mbox{burglary}) = [$perc] .``]
    o  There is a [$fals]% chance of a false alarm.
    [`` P(\mbox{alarm} | \mbox{no burglary}) = [$fperc].``]
    o  Based on local crime statistics, there is a one-in-10,000 chance that a house will be burglarized on a given night:
    [`` P(\mbox{burglary}) = ``] [______]{1/10000}
    o  We are interested in the chance of a burglary given that the alarm has sounded. We can use the conditional probability formula for this:
    [`` P(\mbox{burglary} | \mbox{alarm})
    \ = \ \frac{P(\mbox{burglary, alarm})}{P(\mbox{alarm})}
    \ = \ \frac{P(\mbox{alarm} | \mbox{burglary}) P(\mbox{burglary})}{P(\mbox{alarm})}
    .``]
    o  The one term we don't immediately know is [`P(\mbox{alarm})`].  By the summation rule,
    [``
    P(\mbox{alarm})
    \ = \
    P(\mbox{alarm} | \mbox{burglary}) P(\mbox{burglary}) +
    P(\mbox{alarm} | \mbox{no burglary}) P(\mbox{no burglary})
    .``]
    o  What is [`P(\mbox{alarm})`]?  [_____]{Compute("$perc*0.0001+ $fperc*0.9999")}
    o  What is [`P(\mbox{burglary}, \mbox{alarm})*100`]?  [_____]{Compute("$perc*0.0001*100")}
    o  Putting it all together, using the conditional probability definition mentioned above:
    [`` P(\mbox{burglary} | \mbox{alarm}) = ``]
    [_______________________]{$sol}

    Thus our belief in a burglary has risen approximately a hundredfold from its default value of [`10^{-4}`]  on account of the alarm.

    It is frequently the case, as in this example, that we wish to update the chances of an event [`H`] based on new evidence [`E`]  In other words, we wish to know [`P(H | E)`]
    o  The derivation above implicitly uses the following formula, called Bayes Rule:
    [`` P(H | E)
    \ = \
    \frac{P(E|H) P(H)}{P(E)}.
    ``]


Problem 5

    $p_men = random(6,8,1);
    $p_women = random(3,5,1);
    $p_male_given_colorblind = $p_men/($p_men+$p_women);


    Suppose that there are equal numbers of men and women in the world, and that [$p_men]\% of men
    are colorblind whereas only [$p_women]\% of women are colorblind. A person is chosen at random and found
    to be colorblind. What is the probability that the person is male? [_______________]{$p_men/($p_men+$p_women)}

    Reverse the condition:

    [``
    \begin{align*}
    \textbf{Pr}(\text{male} \ | \ \text{colorblind}) & = \frac{\textbf{Pr}(\text{male},\text{colorblind})}{\textbf{Pr}(\text{colorblind})} \\
    & = \frac{\textbf{Pr}(\text{colorblind} \ | \ \text{male}) \textbf{Pr}(\text{male})}{\textbf{Pr}(\text{colorblind})} \\
    \end{align*}
    ``]

    Law of total probability + Bayes rule:

    [``
    \begin{align*}
    \textbf{Pr}(\text{colorblind}) & = \textbf{Pr}(\text{male},\text{colorblind}) +  \textbf{Pr}(\text{female},\text{colorblind}) \\
    & = \textbf{Pr}(\text{colorblind} \ | \ \text{male}) \textbf{Pr}(\text{male}) + \textbf{Pr}(\text{colorblind} \ | \ \text{female}) \textbf{Pr}(\text{female})
    \end{align*}
    ``]



Problem 6

    *Suppose you have been dealt 4[`\heartsuit`] and 5 [`\heartsuit`]. What is the conditional probability that you will get a straight given that you have been dealt these two cards, and that the flop is "2[`\clubsuit`], Q[`\clubsuit`], K[`\diamondsuit`]"?*
    In this case we need a 3 and either a 6 or A on the turn and river.
    - The number of such card pairs, ignoring order, is [____________]{Compute("4*8")}
    - The conditional probability is [____________]{Compute("4*8/C(52-5,2)")}


Problem 7

    *Find the probability that a poker hand of 5 cards from a standard deck will contain no card smaller than 7 (i.e. 2,3...6) (call this event [`A`]), given that it contains at least one face card (i.e. J, Q, K) (call this event [`B`])"?*

    We define two events:
    * Event [`A`]: The hand contains no card smaller than 7.
    * Event [`B`]: The hand contains at least one face card.

    We first compute the size of the relevant events
    - [`|A \cap B| = `] [____________]{Compute("C(32,5)-C(20,5)")}
    - [`|B| = `] [____________]{Compute("C(52,5)-C(40,5)")}

    We then use the ratio between the sizes of the events to find the conditional probability:
    - The conditional probability [`P(A|B) = `] [____________]{Compute("(C(32,5)-C(20,5))/(C(52,5)-C(40,5))")}


Problem 8

    In Texas Hold'Em, a standard 52-card deck is used. Each player is dealt two cards from the deck face down so that only the player that got the two cards can see them. After checking his two cards, a player places a bet. The dealer then puts 5 cards from the deck face up on the table, this is called the "board" or the "communal cards" because all players can see and used them. The board is layed down in 3 steps: first, the dealer puts 3 cards down (that is called "the flop") followed by two single cards, the first is called "the turn" and the second is called "the river". After the flop, the turn and the river each player can update their bet.  The winner  of the game is the person that can form the strongest 5-card hand from the 2 hand in their hand and the 5 cards in the board.
    ---
    In previous homework you calculated the probability of getting each 5-card hand.
    Here we are interested in something a bit more complex: what is the probability of a particular hand given the cards that are currently available to the player.

    The outcome space in this kind of problem is the set of 7 cards the user has at her disposal after all 5 board cards have been dealt. The size of this space is [`|\Omega|=C(52,7)`]

    Suppose that [`A,B`] are events, i.e. subsets of [`\Omega`]. We will want to calculate conditional probabilities of the type [`P(A|B)`]. Given that the probability of each set of seven cards  is equal to [`1/C(52,7)`] we get that the conditional probability can be expressed as:

    [``P(A|B) = \frac{P(A \cap B)}{P(B)} =
    \frac{\frac{|A \cap B|}{|\Omega|}}{\frac{|B|}{|\Omega|}}
    =\frac{|A \cap B|}{|B|}``]

    Therefore the calculation of conditional probability (for finite sample spaces with uniform distribution) boils down to calculating the ratio between the sizes of two sets.
    ---
    *Suppose you have been dealt "4[`\heartsuit`], 5[`\heartsuit`]".*

    *What is the conditional probability that you will get a straight given that you have been dealt these two cards, and that the flop is "2[`\clubsuit`], 6[`\spadesuit`], K[`\diamondsuit`]"?*
        - Define [`B`] as the set {7-card hands that contain these 5 cards already revealed}.
        - Define [`A`] as the set {7-card hands that contain a straight}.
        The question is asking for [`P(A|B)`]. According to the formula above we need to find [`|A\cap B|`] and [`|B|`].
        - In this case [`A \cap B`] is the set {7-card hands that contain the 5 revealed cards *AND* contain a straight}. To get a straight, the remaining two cards (turn and river) must either be {7,8} or contain 3. We hence define two subsets within [`A \cap B`]:
            - [`S_1`]: {7-card hands that are in [`A \cap B`] *AND* the remaining two cards are 7 and 8, regardless of order}.
                [`|S_1|=`] [____________]{Compute("4^2")}
            - [`S_2`]: {7-card hands that are in [`A \cap B`] *AND* its turn and river contain 3}.
                [`|S_2|=`] [____________]{Compute("C(52-5,2)-C(52-5-4,2)")}
            Because there is no overlap in these two cases ([`S_1 \cap S_2 = \emptyset`]) and these two cases cover all possible valid hands ([`A \cap B = S_1 \cup S_2`]), by definition [`S_1`] and [`S_2`] form a _partition_ of [`A \cap B`], and we have [`|A \cap B| = |S_1| + |S_2|`].
        - Computing [`|B|`] should be easy. 5 cards in the hand are already fixed, we have the freedom of choosing the turn and the river from the 47 cards in the deck. [`|B| = `][______]{Compute("C(47,2)")}.
        - The conditional probability [`P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{|A\cap B|}{|B|} = \frac{|S_1|+|S_2|}{|B|}`] is [____________]{Compute("(C(52-5,2)-C(52-5-4,2)+4^2)/C(52-5,2)")}


Problem 9

    *Like the previous question, suppose you have been dealt "4[`\heartsuit`], 5[`\heartsuit`]".*

    1. *Suppose you have one opponent. What is the conditional probability that you will win, given these two cards in hand, and that the board is "3[`\diamondsuit`], 4[`\diamondsuit`], 4[`\clubsuit`], 4[`\spadesuit`], 5[`\diamondsuit`]"?*
        - With this board, we have four of a kind. The only way the opponent will beat it is with a straight flush. How many possible two cards does the opponent have that can make a straight flush, regardless of order.? [____________]{Compute("3")}
        - The conditional probability that you will win is [____________]{Compute("1-3/C(52-7,2)")}

    2. *What if you have two opponents? What is the conditional probability that you will win?*
        - The conditional probability that you will win is [____________]{Compute("(1-3/C(52-7,2))*(1-3/C(52-9,2))")}


Problem 10

    $n = random(13,16,1);
    $x = random(2,9,1);
    $y = random($x+2,13,1);

    *Three cards are drawn sequentially from a deck that contains [$n] cards numbered 1 to [$n] in an arbitrary order. Suppose the first card drawn is a [$x], what is the probability that the three cards form an increasing sequence?*
        Note that unlike the previous question, we are considering a sequence instead of a set of cards, so the order matters. Define the event of interest, A, as the set of all increasing 3-card sequences, i.e. [`` A = \{(x_1,x_2,x_3) | x_1 < x_2 < x_3\} ``], where [`x_1, x_2, x_3 \in \{1, \cdots, [$n]\}`]. Define event [`B`] as the set of 3-card sequence that starts with [$x], i.e. [`` B = \{(x_1,x_2,x_3) | x_1=[$x]\} ``] or simply [`` B = \{([$x],x_2,x_3) \} ``].
        - [`|B| = `] [____________]{Compute("($n-1)*($n-2)")}.
        It follows that [`` A \cap B = \{([$x],x_2,x_3) | [$x] < x_2 < x_3\} ``]. This set can be partitioned into subsets according to [`x_3`], where in each subset [`x_3`] is a constant: [`` A \cap B = \cup_{x_3 = [$x+2]}^{[$n]} \{([$x],x_2,x_3)|[$x] < x_2 < x_3\} ``].
        Let [`S_{x_3=t}`] represent the subset [`\{([$x],x_2,t)|[$x] < x_2 < t\}`], then [`` |A \cap B| = \sum_{t = [$x+2]}^{[$n]} \left|S_{x_3=t}\right| ``].
        - To compute each [`\left|S_{x_3=t}\right|`], let's start with a specific case, say,  [`t=[$y]`],
            [`\left|S_{x_3=[$y]}\right| = \left| \{([$x],x_2,[$y])|[$x] < x_2 < [$y]\} \right| = `] [_____________]{($y-$x-1)}.
        - Generalize this computation, it should be straightforward to compute [`|A \cap B|`] as the sum of [`S_{x_3=t}`] over all valid [`t`].
            [`|A \cap B|=`][_______________]{($n-$x)*($n-$x-1)/2}
        - Now we are ready to compute the conditional probability [`P(A|B) = `] [______________________]{Compute("($n-$x)*($n-$x-1)/2/(($n-1)*($n-2))")}
