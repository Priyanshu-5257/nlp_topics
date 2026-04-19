Title: Probability 101

URL Source: https://zacharynote.substack.com/p/probability-101

*   **What it is:** A **sample space (S)** is all possible outcomes; an **event (E)** is a subset of those outcomes.

*   **Motivation:** Provides a formal framework to define and organize every possibility in a random process.

**Practice Question:**

Define the Sample Space (S) and the Event (E) for the following scenarios:

*   You draw one marble from our bag. The event is "drawing a primary color (Red or Blue)."

*   You flip two coins. The event is "getting at least one Head."

**Step-by-Step Solution:**

*   **For the marble draw:**

    *   **Sample Space (S):** You have to list every single possible outcome. The bag has 5 Red, 3 Blue, and 2 Green marbles. To be precise, we could label them `S = {R1, R2, R3, R4, R5, B1, B2, B3, G1, G2}`. The size of the sample space is 10.

    *   **Event (E):** We only care about the outcomes that match our description "drawing a primary color." So, we list that subset: `E = {R1, R2, R3, R4, R5, B1, B2, B3}`.

*   **For flipping two coins:**

    *   **Sample Space (S):** List every possible sequence. Let H=Heads, T=Tails. `S = {HH, HT, TH, TT}`.

    *   **Event (E):** We are interested in "getting at least one Head." We look at our sample space and pull out all the outcomes that fit: `E = {HH, HT, TH}`.

*   **What it is:** The three fundamental rules that all probabilities must obey.

    1.   `P(E) ≥ 0` (Non-negativity)

    2.   `P(S) = 1` (Unit Total Probability)

    3.   `P(E₁ ∪ E₂ ∪ ...) = P(E₁) + P(E₂) + ...` (Additivity for disjoint events)

*   **Motivation:** These axioms ensure that probability theory is mathematically consistent and sound.

*   **Intuition:** 1) Probabilities can't be negative. 2) Something must happen (100% chance). 3) If events can't happen at the same time, you can just add their probabilities.

**Practice Question:**

Let's use the experiment of rolling a fair six-sided die. Let event A be "rolling a number less than 3" `{1, 2}` and event B be "rolling a 5" `{5}`. Show how this experiment follows the three axioms.

**Step-by-Step Solution:**

1.   **Axiom 1: Non-negativity**`P(E) ≥ 0`

    *   `P(A)` = (Favorable outcomes for A) / (Total outcomes) = 2/6 = 1/3. This is ≥ 0.

    *   `P(B)` = (Favorable outcomes for B) / (Total outcomes) = 1/6. This is ≥ 0.

    *   The rule holds. Probability can't be negative.

2.   **Axiom 2: Unit Total Probability**`P(S) = 1`

    *   The sample space S is `{1, 2, 3, 4, 5, 6}`.

    *   The probability of rolling any of these numbers is (Total outcomes in S) / (Total outcomes in S) = 6/6 = 1.

    *   The rule holds. Something must happen (you have a 100% chance of rolling a number between 1 and 6).

3.   **Axiom 3: Additivity for disjoint events**

    *   Events A `{1, 2}` and B `{5}` are **disjoint** (or mutually exclusive) because they cannot happen at the same time. You can't roll a 5 and a number less than 3 on a single roll.

    *   The axiom says `P(A ∪ B) = P(A) + P(B)`.

    *   `P(A) = 2/6`. `P(B) = 1/6`.

    *   `P(A) + P(B) = 2/6 + 1/6 = 3/6 = 1/2`.

    *   Let's check this directly. The event "A or B" is "rolling a 1, 2, or 5". This is the set `{1, 2, 5}`, which has 3 outcomes. So, `P(A ∪ B) = 3/6 = 1/2`.

    *   The rule holds. Since the events don't overlap, we can just add their probabilities.

*   **What it is:** Using set theory to describe relationships between events.

    *   **Union (A ∪ B):** Event A _or_ event B occurs.

    *   **Intersection (A ∩ B):** Event A _and_ event B both occur.

    *   **Complement (Aᶜ):** Event A does not occur.

*   **Motivation:** Gives us a precise language to build and manipulate complex events from simpler ones.

*   **Example:** From a deck of cards, let A = "Draw a King" and B = "Draw a Heart".

    *   `A ∪ B`: Drawing a King OR a Heart (13 hearts + 3 other Kings = 16 cards).

    *   `A ∩ B`: Drawing the King of Hearts (1 card).

    *   `Aᶜ`: Drawing any card that is not a King.

**Practice Question:**

From a standard 52-card deck, let event A be "drawing a Face Card" (Jack, Queen, King) and event B be "drawing a Diamond". Describe the following events and find how many cards are in each set.

1.   `A ∩ B` (A and B)

2.   `A ∪ B` (A or B)

3.   `Bᶜ` (Not B)

**Step-by-Step Solution:**

1.   `A ∩ B`**(Intersection):**

    *   **Meaning:** The cards that are **both** Face Cards **and** Diamonds.

    *   **Outcomes:** Jack of Diamonds, Queen of Diamonds, King of Diamonds.

    *   **Count:** 3 cards.

2.   `A ∪ B`**(Union):**

    *   **Meaning:** The cards that are **either** a Face Card **or** a Diamond (or both).

    *   **Outcomes:** This includes all 13 Diamonds, plus the Face Cards from the other three suits (Hearts, Clubs, Spades).

    *   **Count:** There are 13 Diamonds. There are 12 Face Cards in total (3 in each of 4 suits). The 3 Diamond Face Cards are already counted in the "13 Diamonds". So, we need to add the other 3x3 = 9 Face Cards. Total = 13 + 9 = 22 cards.

3.   `Bᶜ`**(Complement):**

    *   **Meaning:** The cards that are **not** Diamonds.

    *   **Outcomes:** All the Hearts, Clubs, and Spades.

    *   **Count:** There are 13 cards in each of the three other suits. Total = 13 + 13 + 13 = 39 cards. (Or more simply, 52 total cards - 13 Diamonds = 39).

*   **What it is:** Techniques to count possible outcomes, essential for `P(E) = Favorable / Total`.

    *   **Permutation (Order matters):**`P(n, k) = n! / (n-k)!`

    *   **Combination (Order doesn't matter):**`C(n, k) = n! / (k!(n-k)!)`

*   **Motivation:** It's often impossible to list all outcomes manually. These formulas are critical shortcuts.

*   **Example:** A club has 10 members.

    *   **Permutation:** How many ways can we choose a President, VP, and Treasurer? Order matters. `P(10, 3) = 10! / (10-3)! = 10 * 9 * 8 = 720` ways.

    *   **Combination:** How many ways can we choose a 3-person committee? Order doesn't matter. `C(10, 3) = 10! / (3!(10-3)!) = (10 * 9 * 8) / (3 * 2 * 1) = 120` ways.

**Practice Question:**

Our club has 10 members.

1.   We need to select a 3-person committee. How many different committees are possible?

2.   We need to elect a President, a Vice President, and a Secretary. How many different ways can these roles be filled?

**Step-by-Step Solution:**

1.   **The Committee:**

    *   **Analyze:** Does order matter here? If we choose Alice, Bob, and Charlie for the committee, is that different from choosing Charlie, Alice, and Bob? No, it's the same group of people. So, **order does not matter**.

    *   **Method:** This is a **Combination**. We are choosing `k=3` people from `n=10`.

    *   **Calculation:**`C(10, 3) = 10! / (3! * (10-3)!) = 10! / (3! * 7!) = (10 * 9 * 8) / (3 * 2 * 1) = 720 / 6 = **120** possible committees.`

2.   **The Officers:**

    *   **Analyze:** Does order matter? If we choose Alice for President, Bob for VP, and Charlie for Secretary, is that different from choosing Charlie for President, Alice for VP, and Bob for Secretary? Yes, these are completely different outcomes. So, **order matters**.

    *   **Method:** This is a **Permutation**. We are arranging `k=3` people from `n=10` into specific roles.

    *   **Calculation:**`P(10, 3) = 10! / (10-3)! = 10! / 7! = 10 * 9 * 8 = **720** possible arrangements.`

*   **What it is:**`P(Aᶜ) = 1 - P(A)`

*   **Motivation:** Calculating the probability of what you _don't_ want is often much easier.

*   **Why it's true:** An event A and its complement Aᶜ are mutually exclusive (can't both happen) and exhaustive (one of them must happen). Therefore, `P(A) + P(Aᶜ) = P(S) = 1`. The rule comes from rearranging this equation.

**Practice Question:**

You flip 3 fair coins. What is the probability of getting **at least one** Head?

**Step-by-Step Solution:**

1.   **Direct Method (The Hard Way):**

    *   Let A be the event "at least one Head". This means we could get 1 Head, 2 Heads, or 3 Heads.

    *   The sample space is {HHH, HHT, HTH, THH, HTT, THT, TTH, TTT}, with 8 outcomes.

    *   Outcomes with at least one head: {HHH, HHT, HTH, THH, HTT, THT, TTH}. There are 7 of them.

    *   So, `P(A) = 7/8`.

2.   **Complement Rule (The Easy Way):**

    *   Let A be the event "at least one Head".

    *   The complement, `Aᶜ`, is the event that you do **not** get at least one head. This means you get **zero** heads.

    *   What is the outcome for `Aᶜ`? It's {TTT}. There is only 1 outcome.

    *   The probability of the complement is `P(Aᶜ) = 1/8`.

    *   The Complement Rule states `P(A) = 1 - P(Aᶜ)`.

    *   `P(A) = 1 - 1/8 = **7/8**`.

This was much faster because the complement event was a single, easy-to-calculate outcome.

*   **What it is:**`P(A ∪ B) = P(A) + P(B) - P(A ∩ B)`

*   **Motivation:** The correct way to find the probability of combined "OR" events.

*   **Intuition:** If you just add `P(A)` and `P(B)`, you've double-counted the outcomes where they _both_ happen. The `P(A ∩ B)` term is the overlap, so you must subtract it once to correct for the double-counting.

**Practice Question:**

You draw one card from a 52-card deck. What is the probability that the card is a **Club or a Queen**?

**Step-by-Step Solution:**

1.   **Define Events:**

    *   Let A be "drawing a Club".

    *   Let B be "drawing a Queen".

2.   **Find Probabilities:**

    *   `P(A)`: There are 13 Clubs in the deck. So, `P(A) = 13/52`.

    *   `P(B)`: There are 4 Queens in the deck. So, `P(B) = 4/52`.

3.   **Identify the Overlap (Intersection):**

    *   Is there an outcome that is **both** a Club **and** a Queen? Yes, the Queen of Clubs.

    *   The intersection `A ∩ B` is "drawing the Queen of Clubs".

    *   `P(A ∩ B) = 1/52`.

4.   **Apply the Addition Rule:**

    *   `P(A ∪ B) = P(A) + P(B) - P(A ∩ B)`

    *   `P(A ∪ B) = 13/52 + 4/52 - 1/52`

    *   `P(A ∪ B) = 16/52 = 4/13`.

**Intuition Check:** There are 13 Clubs. There are 3 other Queens (Hearts, Diamonds, Spades). 13 + 3 = 16 favorable cards. 16/52. It works.

*   **What it is:** The probability of A, given that B has already occurred. `P(A|B) = P(A ∩ B) / P(B)`

*   **Motivation:** The mathematical way to update our knowledge. As we learn new information, probabilities change.

*   **Intuition:** We are no longer in the original sample space `S`. Our new universe of possibilities is just the outcomes where `B` happened. Within that smaller universe, we find the fraction where `A`_also_ happens.

*   **Example:** You draw one card and see it is a King (`B`). What is the probability it is the King of Hearts (`A`)?

    *   The new sample space is just the 4 Kings. `P(B) = 4/52`.

    *   `A ∩ B` is "King of Hearts and a King", which is just "King of Hearts". `P(A ∩ B) = 1/52`.

    *   `P(King of Hearts | King) = (1/52) / (4/52) = 1/4`. This makes intuitive sense.

**Practice Question (Walk-through):**

Imagine you draw two marbles from our bag (5 Red, 3 Blue, 2 Green) **without replacement**. You draw the first marble and see that it is **Blue**. Given this information, what is the probability that the second marble you draw is Red?

**Step-by-Step Walk-through:**

1.   **Define the Events:**

    *   Let B₁ be the event "the first marble is Blue".

    *   Let R₂ be the event "the second marble is Red".

    *   We want to find `P(R₂ | B₁)`. This reads "the probability of R₂ _given_ that B₁ has already happened."

2.   **Think Intuitively (The Shrinking Sample Space):**

    *   Before we drew any marbles, there were 10 in the bag.

    *   But we _know_ the first one was Blue. This is a fact. So, we are no longer in the original universe of 10 marbles.

    *   Our new universe (our new sample space) is the bag _after_ one Blue marble has been removed.

    *   What does that new bag look like? It now has **9** marbles in total.

    *   How many of each color? 5 Red, **2** Blue, and 2 Green.

    *   Now, from this new bag, what is the probability of drawing a Red marble?

    *   There are 5 Red marbles out of a new total of 9.

    *   So, `P(R₂ | B₁) = **5/9**`.

3.   **Use the Formula (to confirm):**

    *   The formula is `P(R₂ | B₁) = P(R₂ ∩ B₁) / P(B₁)`.

    *   `P(B₁)` (Prob. the first is Blue) = 3/10.

    *   `P(R₂ ∩ B₁)` (Prob. the first is Blue AND the second is Red). We can find this using the multiplication rule (covered next): `P(B₁) * P(R₂ | B₁) = (3/10) * (5/9) = 15/90 = 1/6`.

    *   Let's apply the formula: `P(R₂ | B₁) = (1/6) / (3/10) = 1/6 * 10/3 = 10/18 = **5/9**`.

    *   The result is the same. The intuitive "shrinking sample space" approach is often easier for simple problems.

*   **Multiplication Rule:** Finds the probability of A _and_ B both occurring. `P(A ∩ B) = P(A|B) * P(B)`

    *   **Why it's true:** This is not a new concept, just an algebraic rearrangement of the conditional probability formula.

*   **Independence:** Two events A and B are independent if one doesn't affect the other.

    *   **Formal Definition:**`P(A|B) = P(A)`

    *   **Practical Test:**`P(A ∩ B) = P(A) * P(B)`

*   **Motivation:** Independence is a powerful simplifying assumption. If events are independent, the math becomes much easier—you can just multiply their probabilities.

*   **Common Confusion:** Independent events are NOT mutually exclusive. If A and B are mutually exclusive (e.g., rolling a 1 and a 6), they are highly _dependent_—if you roll a 1, the probability of rolling a 6 becomes 0.

*   **Example:** You roll a die (A) and flip a coin (B). What is `P(roll a 6 and get Heads)`?

    *   These events are independent. `P(roll 6) = 1/6`. `P(Heads) = 1/2`.

    *   `P(6 ∩ Heads) = P(6) * P(Heads) = 1/6 * 1/2 = 1/12`.

**Practice Question:**

Compare these two scenarios:

a) You roll a die twice. What is the probability of rolling a 6 on the first roll **and** a 6 on the second roll? b) You draw two cards from a deck **without replacement**. What is the probability of drawing a King on the first draw **and** a King on the second draw?

**Step-by-Step Solution:**

a) **Rolling a Die Twice:** * **Analyze:** Does the outcome of the first roll affect the probability of the second roll? No. The die doesn't remember what it rolled before. The events are **INDEPENDENT**. * **Method:** We can use the simplified multiplication rule for independent events: `P(A ∩ B) = P(A) * P(B)`. * **Calculation:** * `P(1st is a 6) = 1/6`. * `P(2nd is a 6) = 1/6`. * `P(1st is 6 AND 2nd is 6) = (1/6) * (1/6) = **1/36**`.

b) **Drawing Two Cards without Replacement:** * **Analyze:** Does the outcome of the first draw affect the probability of the second draw? Yes. Because we don't put the first card back, the deck has changed (51 cards remain). The events are **DEPENDENT**. * **Method:** We must use the general multiplication rule: `P(A ∩ B) = P(A) * P(B | A)`. * **Calculation:** * Let A be "1st card is a King". `P(A) = 4/52`. * Let B be "2nd card is a King". We need `P(B | A)`, the probability the second is a King _given_ the first was a King. * After drawing one King, there are only **3** Kings left in a deck of **51** cards. So, `P(B | A) = 3/51`. * `P(A ∩ B) = (4/52) * (3/51) = 12/2652 ≈ 0.0045`.

**Key Difference:** In (a), the probability of the second event was just `P(B)`. In (b), it was `P(B|A)` because the first event changed the situation.

*   **What it is:** A variable that assigns a number to every outcome in the sample space.

*   **Motivation:** Allows us to use the powerful tools of mathematics (algebra, calculus) on the outcomes of a random process, rather than just describing them with words.

*   **Example:** Experiment: Flip 3 coins. The sample space S = {HHH, HHT, HTH, THH, HTT, THT, TTH, TTT}.

    *   Let's define a random variable `X = the number of heads`.

    *   If the outcome is HHH, `X = 3`.

    *   If the outcome is HTH, `X = 2`.

    *   If the outcome is TTT, `X = 0`.

    *   The event "getting 2 heads" is now concisely written as `P(X=2)`.

**Practice Question:**

Let's play a simple game. You flip two coins. For every Head you get, you win $5. For every Tail, you lose $2. Let the random variable `X` be your total winnings. What are the possible values of `X`?

**Step-by-Step Solution:**

1.   **List the Outcomes:** The sample space of flipping two coins is `S = {HH, HT, TH, TT}`.

2.   **Map Each Outcome to a Number:** We apply the rules of the game to each outcome to find the value of `X`.

    *   **Outcome HH:** You get two Heads. Winnings = $5 + $5 = $10. So, for HH, `X = 10`.

    *   **Outcome HT:** One Head, one Tail. Winnings = $5 - $2 = $3. For HT, `X = 3`.

    *   **Outcome TH:** One Tail, one Head. Winnings = -$2 + $5 = $3. For TH, `X = 3`.

    *   **Outcome TT:** Two Tails. Winnings = -$2 - $2 = -$4. For TT, `X = -4`.

3.   **State the Possible Values of X:** The random variable `X` can take on the values from the set `{10, 3, -4}`. Now we can ask questions like `P(X=3)`, which we can see is 2/4 = 1/2.

*   **What it is:** Describing probabilities when more than one random variable is involved.

    *   **Joint Probability**`P(X=x, Y=y)`**:** The probability of a specific outcome for X _and_ a specific outcome for Y.

    *   **Marginal Probability**`P(X=x)`**:** The probability of a specific outcome for X, regardless of what Y is.

*   **Motivation:** To understand and quantify the relationship between different random factors.

*   **Intuition:** Imagine a table of all possibilities. The joint probabilities are the cells inside the table. The marginal probabilities are the totals in the "margins" (the sums of the rows and columns).

*   **Example:** Roll a red die (R) and a blue die (B). There are 36 outcomes.

    *   **Joint:**`P(R=1, B=6)` = The probability of rolling a 1 on red AND a 6 on blue. This is one specific outcome out of 36, so the probability is `1/36`.

    *   **Marginal:**`P(R=1)` = The probability of rolling a 1 on red, no matter what the blue die shows. You can get (1,1), (1,2), (1,3), (1,4), (1,5), or (1,6). There are 6 favorable outcomes out of 36 total. So `P(R=1) = 6/36 = 1/6`. This is found by summing the joint probabilities: `P(R=1) = Σ P(R=1, B=b)` for all b from 1 to 6.

**Practice Question:**

A coffee shop observes that 100 customers buying one drink chose the following:

SmallMediumLarge**Coffee**203010**Tea**10155**Espresso**550

Let `D` be the random variable for Drink Type and `S` be for Size.

*   Fill in the "margins" of the table (the row and column totals).

*   What is the **joint probability**`P(D=Coffee, S=Medium)`?

*   What is the **marginal probability**`P(D=Tea)`?

**Step-by-Step Solution:**

*   **Fill in the Margins:** We just sum the rows and columns.

SmallMediumLarge**Total (Marginal for D)Coffee**20301060**Tea**1015530**Espresso**55010**Total (Marginal for S)355015100**

*   **Joint Probability**`P(D=Coffee, S=Medium)`**:**

    *   **Meaning:** This is the probability of one specific combination happening.

    *   **How to find:** Look at the single cell where "Coffee" and "Medium" intersect. The value is 30.

    *   **Calculation:**`P(D=Coffee, S=Medium) = 30 / 100 = 0.3`.

*   **Marginal Probability**`P(D=Tea)`**:**

    *   **Meaning:** This is the overall probability of someone ordering Tea, regardless of the size.

    *   **How to find:** Look in the "margin" at the end of the "Tea" row. The total is 30.

    *   **Calculation:**`P(D=Tea) = 30 / 100 = 0.3`. This comes from summing the joint probabilities in that row: `P(Tea, Small) + P(Tea, Medium) + P(Tea, Large) = 10/100 + 15/100 + 5/100 = 30/100`.

*   **What it is:** The long-run average value of a random variable.

    *   **Discrete Formula (PMF):**`E[X] = Σ [x * P(X=x)]` where P(X=x) is the Probability Mass Function

    *   **Continuous Formula (PDF):**`E[X] = ∫ x * f(x) dx` where f(x) is the Probability Density Function

*   **Motivation:** It's the single most important number for summarizing a random variable's distribution. It tells you its "center of mass."

*   **Takeaway:** The expected value does not have to be a possible outcome.

*   **Example:** What is the expected value of a single roll of a fair six-sided die?

    *   `E[X] = (1 * P(X=1)) + (2 * P(X=2)) + ... + (6 * P(X=6))`

    *   `E[X] = (1 * 1/6) + (2 * 1/6) + (3 * 1/6) + (4 * 1/6) + (5 * 1/6) + (6 * 1/6)`

    *   `E[X] = (1+2+3+4+5+6) / 6 = 21 / 6 = 3.5`.

**Practice Question:**

You play a game where you roll a single die.

*   If you roll a 6, you win $12.

*   If you roll a 4 or 5, you win $3.

*   If you roll a 1, 2, or 3, you lose $6. What is the expected value of playing this game once? Is it a good game to play?

**Step-by-Step Solution:**

1.   **Identify the Random Variable and its Probabilities:**

    *   Let `X` be your winnings from one play. The possible values of `X` are {+12, +3, -6}.

    *   `P(X = 12)` (rolling a 6) = 1/6.

    *   `P(X = 3)` (rolling a 4 or 5) = 2/6 = 1/3.

    *   `P(X = -6)` (rolling a 1, 2, or 3) = 3/6 = 1/2.

2.   **Apply the Expectation Formula:**

    *   The formula is `E[X] = Σ [x * P(X=x)]`.

    *   `E[X] = (12 * P(X=12)) + (3 * P(X=3)) + (-6 * P(X=-6))`

    *   `E[X] = (12 * 1/6) + (3 * 1/3) + (-6 * 1/2)`

3.   **Calculate:**

    *   `E[X] = 2 + 1 - 3`

    *   `E[X] = $0`

**Conclusion:** The expected value is $0. This means that if you played this game thousands of times, you would expect to break even. It is a "fair" game, neither good nor bad for you in the long run.

*   **What it is:** For outcomes on a continuous range (e.g., time, distance), where there are infinite possibilities.

    *   **Probability Calculation:**`P(a ≤ X ≤ b) = ∫[a to b] f(x) dx`, where `f(x)` is the Probability Density Function (PDF).

*   **Motivation:** The world isn't just countable events like coin flips. We need to model things like arrival times, sensor measurements, and physical dimensions.

**Aspect, Discrete Variables, Continuous Variables

Sample Space,**Countable (e.g., {1,2,3,4,5,6})**,**Uncountable (e.g., [0,10] interval)

**Probability Function,**PMF: P(X=x)**,**PDF: f(x)

**Point Probability,**P(X=x) > 0 possible**,**P(X=x) = 0 always

**Calculation Method,**Summation: Σ P(X=x)**,**Integration: ∫ f(x) dx

**Examples,**Dice rolls, coin flips**,**Time, distance, temperature

*   **Intuition:** Think of throwing a dart at a line from 0 to 10. The chance of hitting _exactly_ 5.000... is zero. It's like a line having zero width. We can only talk about the probability of the dart landing in an _interval_, like between 5 and 6. This probability is the _area_ under the PDF curve for that interval.

*   **Most Important Property:** For any continuous variable X, `P(X = c) = 0`.

*   **Example:** A bus arrives uniformly between 0 and 10 minutes past the hour. This means its PDF is a flat line `f(x) = 1/10` for `x` in. What's the probability it arrives in the first 2 minutes?

    *   We want `P(0 ≤ X ≤ 2)`. This is the area of a rectangle with width (2-0)=2 and height 1/10.

    *   Area = `2 * (1/10) = 0.2` or 20%.

**Practice Question (Walk-through):**

A automated baker cuts loaves of bread. The length of a loaf, X, is uniformly distributed between 14 inches and 18 inches. This means the probability density function (PDF) is a flat line over that interval.

*   What is the height of this PDF, `f(x)`?

*   What is the probability that a randomly selected loaf is between 15 and 17 inches long?

*   What is the probability that a loaf is _exactly_ 16 inches long?

**Step-by-Step Walk-through:**

1.   **Analyze the PDF:**

    *   The variable `X` exists on the range. The width of this range is `18 - 14 = 4` inches.

    *   For a PDF, the total area under the curve must equal 1 (representing 100% probability).

    *   Since our PDF is a rectangle (uniform distribution), its area is `width * height`.

    *   `4 * height = 1`.

    *   Solving for the height gives `height = 1/4`. So, `f(x) = 1/4`**for**`14 ≤ x ≤ 18` (and 0 otherwise). This answers part (a).

2.   **Calculate the Probability for an Interval**`P(15 ≤ X ≤ 17)`**:**

    *   This probability is the area under our PDF curve between `x=15` and `x=17`.

    *   This is another rectangle.

    *   The **width** of this interval is `17 - 15 = 2`.

    *   The **height** of the PDF is constant at `1/4`.

    *   **Area = width * height = 2 * (1/4) = 2/4 = 0.5**.

    *   There is a 50% chance the loaf is between 15 and 17 inches long.

3.   **Calculate the Probability at an Exact Point**`P(X = 16)`**:**

    *   This is the most important concept for continuous variables. An exact point corresponds to an interval with a width of zero.

    *   The "area" would be `width * height = 0 * (1/4) = 0`.

    *   **The probability of a continuous random variable taking on any single, exact value is always 0.**

*   **What it is:** A way to find a probability by breaking the sample space into several non-overlapping pieces.

    *   **Formula:**`P(A) = Σ P(A|Bᵢ) * P(Bᵢ)`

*   **Motivation:** It allows you to calculate a difficult probability (`P(A)`) by finding a set of simpler conditional probabilities (`P(A|Bᵢ)`). It's a "divide and conquer" strategy.

*   **Example:** You have two bags of marbles. Bag 1 has 3 red and 7 blue. Bag 2 has 6 red and 4 blue. You pick a bag at random (50/50 chance) and then draw one marble. What is `P(Red)`?

    *   Let A be "draw a red marble". Let B₁ be "picked Bag 1" and B₂ be "picked Bag 2".

    *   `P(Red) = P(Red | Bag 1) * P(Bag 1) + P(Red | Bag 2) * P(Bag 2)`

    *   `P(Red) = (3/10) * (1/2) + (6/10) * (1/2)`

    *   `P(Red) = 3/20 + 6/20 = 9/20 = 0.45`.

**Practice Question (Walk-through):**

Let's return to our bags of marbles.

*   **Bag A** has: 5 Red, 5 Blue.

*   **Bag B** has: 1 Red, 7 Blue.

You have a 70% chance of picking Bag A and a 30% chance of picking Bag B. You pick a bag at random and then draw one marble. What is the overall probability that you draw a **Blue** marble?

**Step-by-Step Walk-through:**

1.   **Define Events:**

    *   Let `Blue` be the event "the drawn marble is Blue". This is what we want to find, `P(Blue)`.

    *   Let `A` be the event "you chose Bag A". `P(A) = 0.7`.

    *   Let `B` be the event "you chose Bag B". `P(B) = 0.3`.

    *   Events `A` and `B` form a **partition** of the sample space; you must choose one of them, and they are mutually exclusive.

2.   **Find the Conditional Probabilities:**

    *   We need the probability of drawing a Blue marble _given_ each scenario.

    *   `P(Blue | A)` (Prob. of Blue, given you have Bag A) = 5 Blue / 10 total = 0.5.

    *   `P(Blue | B)` (Prob. of Blue, given you have Bag B) = 7 Blue / 8 total = 0.875.

3.   **Apply the Law of Total Probability:**

    *   The formula is `P(Blue) = P(Blue | A) * P(A) + P(Blue | B) * P(B)`.

    *   This translates to: (Prob. of getting a Blue via Bag A) + (Prob. of getting a Blue via Bag B).

    *   `P(Blue) = (0.5 * 0.7) + (0.875 * 0.3)`

4.   **Calculate:**

    *   `P(Blue) = 0.35 + 0.2625`

    *   `P(Blue) = **0.6125**`

So, the overall probability of drawing a blue marble is 61.25%.

*   **What it is:** The formula that "flips" conditional probabilities: `P(A|B) = (P(B|A) * P(A)) / P(B)`

*   **Motivation:** This is the engine of learning and inference in AI. It tells you how to update your belief about a hypothesis (`A`) after you see new evidence (`B`).

*   **Intuition:**

    *   `P(A)` = **Prior**: How much you believed A was true _before_ the evidence.

    *   `P(A|B)` = **Posterior**: Your updated belief in A _after_ seeing evidence B.

    *   `P(B|A)` = **Likelihood**: How likely you would be to see this evidence if A were true.

*   **Why it's true:** It comes directly from the two ways to write the multiplication rule: `P(A ∩ B) = P(A|B)P(B)` and `P(A ∩ B) = P(B|A)P(A)`. Set them equal and divide by `P(B)`.

*   **Example:** A disease test is 99% accurate (if you have the disease, it's positive 99% of the time; if you don't, it's negative 99% of the time). 1% of the population has the disease. You test positive. What's the probability you actually have the disease?

    *   A = Have Disease. B = Test Positive. We want `P(A|B)`.

    *   `P(A)` = 0.01 (Prior)

    *   `P(B|A)` = 0.99 (Likelihood)

    *   `P(B)` needs the Law of Total Probability: `P(B) = P(B|A)P(A) + P(B|Aᶜ)P(Aᶜ)``P(B) = (0.99 * 0.01) + (0.01 * 0.99) = 0.0198`

    *   `P(A|B) = (0.99 * 0.01) / 0.0198 ≈ 0.5`.

    *   **Takeaway:** Even with a positive result from a 99% accurate test, you only have a 50% chance of having the disease! This is because the base rate of the disease is so low.

**Practice Question (Walk-through):**

Let's use the same two-bag setup from the previous question.

*   **Bag A** (70% chance): 5 Red, 5 Blue.

*   **Bag B** (30% chance): 1 Red, 7 Blue.

You didn't see which bag was chosen. Your friend reaches in, draws a marble, and shows it to you. **It's a Blue marble.** What is the probability that the marble came from **Bag A**?

**Step-by-Step Walk-through:**

1.   **Define the Goal:** We want to find `P(A | Blue)`.

    *   **Hypothesis:** The marble came from Bag A. Our _prior_ belief in this was `P(A) = 0.7`.

    *   **Evidence:** The marble is Blue.

    *   **Goal (Posterior):** Update our belief about the bag, _given_ the evidence we've seen.

2.   **Write Down Bayes' Rule:**

    *   `P(A | Blue) = (P(Blue | A) * P(A)) / P(Blue)`

3.   **Gather the Components:**

    *   `P(Blue | A)` (Likelihood): The probability of getting our evidence (Blue) if our hypothesis (Bag A) is true. We calculated this in the last problem: `P(Blue | A) = 0.5`.

    *   `P(A)` (Prior): Our belief that we chose Bag A _before_ seeing the marble. `P(A) = 0.7`.

    *   `P(Blue)` (Total Probability of the Evidence): The overall probability of drawing a Blue marble, regardless of the bag. We calculated this using the Law of Total Probability in the previous question! `P(Blue) = 0.6125`.

4.   **Substitute and Calculate:**

    *   `P(A | Blue) = (0.5 * 0.7) / 0.6125`

    *   `P(A | Blue) = 0.35 / 0.6125`

    *   `P(A | Blue) ≈ 0.5714`

**Conclusion:** Before we saw the marble, the probability of it being Bag A was 70%. After seeing a Blue marble, our belief that it's Bag A has dropped to about 57%. This makes sense, because drawing a Blue marble is more likely from Bag B than from Bag A, so seeing a Blue marble provides some evidence in favor of Bag B.

*   **What it is:** A problem-solving technique where you define the answer in terms of itself.

*   **Motivation:** Turns complex, infinite-sum problems into simple algebra. It's perfect for sequential "wait until X happens" problems where the process is "memoryless" (past failures don't change future probabilities).

*   **Key Challenge:** The outcome space is infinitely large, making direct calculation impossible. For example, when flipping until first heads, possible outcomes are: {H, TH, TTH, TTTH, TTTTH, ...} - theoretically infinite sequences.

*   **Why it's still calculable:** Even though there are infinite outcomes, each has exponentially decreasing probability. P(H)=1/2, P(TH)=1/4, P(TTH)=1/8, etc. The infinite sum converges: 1/2 + 1/4 + 1/8 + ... = 1. Recursion elegantly sidesteps this infinite calculation by using self-reference.

*   **Example:** How many times do you expect to flip a coin until you get heads?

    *   Let `E` be the expected number of flips.

    *   You flip once. This always costs you `1` flip.

    *   There's a 1/2 chance it's Heads, and the game is over (0 more flips needed).

    *   There's a 1/2 chance it's Tails, and you're back to square one. You still expect to need `E` more flips from this point.

    *   The equation is: `E = 1 + (1/2 * 0) + (1/2 * E)`

    *   `E = 1 + E/2`

    *   `E/2 = 1`

    *   `E = 2`. You expect to need 2 flips.

**Practice Question (Walk-through):**

Let's modify the coin flip game. What is the expected number of flips you need to get **two Heads in a row** (HH)?

**Step-by-Step Walk-through:**

1.   **Define the States and Expected Values:**

    *   Let `E` be the expected number of flips starting from scratch (no recent Heads). This is our goal.

    *   Let `E_H` be the expected number of _additional_ flips needed once we have just seen one Head. From this state, we need just one more Head to win.

2.   **Set up the Equations by Taking One Step:**

    *   **Equation for E (starting from scratch):**

        *   We must flip the coin once (this costs `1` flip).

        *   With probability 1/2, we get Tails (T). We've made no progress. We're back to the start, and we still expect to need `E` more flips. Cost: `1/2 * E`.

        *   With probability 1/2, we get Heads (H). We've made progress! We are now in state H, and we expect to need `E_H` more flips. Cost: `1/2 * E_H`.

        *   **Equation 1:**`E = 1 + (1/2 * E) + (1/2 * E_H)`

    *   **Equation for E_H (we just saw a Head):**

        *   We flip the coin once more (this costs `1` flip).

        *   With probability 1/2, we get Heads (H). We got HH! The game is over. We need 0 more flips. Cost: `1/2 * 0`.

        *   With probability 1/2, we get Tails (T). We broke our streak (HT). We are back to square one, needing `E` more flips. Cost: `1/2 * E`.

        *   **Equation 2:**`E_H = 1 + (1/2 * 0) + (1/2 * E)`

3.   **Solve the System of Equations:**

    *   First, simplify Equation 2: `E_H = 1 + E/2`.

    *   Now, substitute this expression for `E_H` into Equation 1:

        *   `E = 1 + E/2 + 1/2 * (1 + E/2)`

    *   Now, solve for E using algebra:

        *   `E = 1 + E/2 + 1/2 + E/4`

        *   `E = 3/2 + 3E/4`

        *   `E - 3E/4 = 3/2`

        *   `E/4 = 3/2`

        *   `E = 4 * (3/2) = 12 / 2 = 6`

**Conclusion:** You expect to need **6** flips to get two heads in a row.