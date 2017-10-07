---
title: 'Probability and Expectation (Part 1)'
published: true
date: '17:19 11/12/2013'
taxonomy:
    category:
        - blog
    tag:
        - probability
        - expectation
body_classes: 'header-lite fullwidth blogstyling'
---

"Probability is one of the misunderstood subject on earth" - I heard it from someone's lecture. Since it is comparatively tough to understand so being author of this article even I can't I am proficient to calculate probability in any situation. My strategy is to learn basics of it and apply those basics on various problems until I get enough skills to move forward on complex stuffs like statistics, better part of which is probability. Anyway as this article based on basic probability I can't deny to write down definition of probability by no means but I want to ignore any formal definition of it rather here is few informal definition(s):

> Probability is the chance that something will happen - how likely it is that some event will occur. - From [Math is Fun](https://www.mathsisfun.com/definitions/probability.html)
> 
> Probability is the measure of the likelihood that an event will occur. - From [Wiki](https://en.wikipedia.org/wiki/Probability)
> 
> According to me, probability gives us a limit of certainty along with a limit of un-certainty though. As people like to find certainty in real life, probability becomes popular topic to study to increase certainty in special situations where prediction or emotion don't work well

One more important information which is missed in definition is - probability is measured from 0 to 1 or you could say by percentage. Anyway I guess to study probability it's important to collect examples and make sense from those examples. So lets go through examples one by one.

###### Example 1 (An unbaised coin):
This is the simplest example of probability. Suppose you have a coin (unbaised) with 2 faces head and tail. If you toss the coin what is the chances of getting head ? It's 50-50. So answer is : 0.5. See solution section for more explanation.

###### Example 2 (Single dice):
Suppose you have a dice (unbaised) with 6 faces and faces are numbered from 1 to 6. If you roll the dice what are chances you get a face written 5 on it ? 

###### Example 3 (Two dices):
Let's make another example by extending previous example. Suppose you are a gambler and you have basic knowledge of probability. Your friend is nearby to you and you want to make some money by a simple gamble game. Game rule is, there are 2 dices (unbaised) and both of you have to pick a number between 1 and 12. After picking a number each one have to roll 2 dices one after one. In this game you picked the number 7 based on probability. Question is how did you calculate probability in this game to pick 7.

###### Example 4 (Birthday problem):
Its well-known and famous [Birthday problem](https://en.wikipedia.org/wiki/Birthday_problem). Suppose 1 year has 365 days. You invited friends into your birthday party and there are total 23 people including you in the party. What are chances any two of these people have same birthday ?

###### Example 5 (Monty Hall problem):
Its more famous than the previous one [Monty Hall problem](https://en.wikipedia.org/wiki/Monty_Hall_problem). In fact it's brain teaser because most of the mathematicians were confused in early stage of this problem and that's why it was considered as a dilemma. However it's not a dilemma anymore as it's proved in several ways using probability theory. Here is problem statement:

> **Suppose you're on a game show, and you're given the choice of three doors: Behind one door is a car; behind the others, goats. You pick a door, say No. 1, and the host, who knows what's behind the doors, opens another door, say No. 3, which has a goat. He then says to you, "Do you want to pick door No. 2?" Is it to your advantage to switch your choice?**

---

Before going to solve above example it's required to basic rules of probability.

###### Independent Probability:
This rule is applicable when two events occur and don't depend on each other. Suppose you tossed a coin 2 times. Here 1st time toss doesn't affect 2nd time toss. So these 2 events are independent. The rule is simple. When you need to know probability of 2 independent events you need to multiply probability of each independent event. Suppose probability of getting 2 heads by doing 2 coin toss. For each event probability is 0.5. So probability for 2 events is 0.5 * 0.5 = 0.25. Mathematically here is formula:

> **P( A and B ) = P(A) . P(B)**

You could verify this by generating sample space and your desired result.

> Sample space will be `[TT], [HT], [TH], [HH]`. Count = 4
> 
> Your desired result is `[HH]`. Count = 1
> 
> Probability = 1/4


###### Mutually Exclusive:
If an event discard another event then these two events are mutually exclusive. In other words, if two events can't happen at a time then they are mutually exclusive. A very simple example is, you are given a dice with 6 faces to roll once what are chances to get 3 or 5 ? In this case if we get 3 we can't get 5 and vice versa. Formula is:

> **P ( A or B ) = P(A) + P(B)**

For N independent events:

> **P( A<sub>1</sub> or A<sub>2</sub> or A<sub>3</sub> or ........ or A<sub>n</sub>) = P(A<sub>1</sub>) + P(A<sub>2</sub>) + P(A<sub>3</sub>) + ............... + P(A<sub>n</sub>)**


###### Not Mutually Exclusive:
If one event influences another event or you could consider there are common chances in these 2 events they aren't independent events and that's their probability shouldn't be calculated as mutually exclusive event. Because have to discard value of common probability of these events. Isn't ? This idea comes from set theory. So here is formula:

> **P ( A or B ) = P(A) + P(B) - P( A and B )**

You could verify this with a sample example of a dice with 6 faces. When dice rolled what are chances to get a even number or a number greater than 3? > ?> > 

> Probability of getting a even number is: 3/6 `[2, 4, 6]`
> 
> Probability of getting a number greater than 3 is: 3/6 `[4, 5, 6]`
> 
> Probability of getting a number which is both even and greater than 3 is: 2/6 `[4, 6]`
> 
> So answer is : 3/6 + 3/6 - 2/6 = 4/6 = 2/3 = 67%


###### Conditional Probability:
First of all I like conditional probability because it increases probability in some extent. This is easy to understand with a sample example of dice roll. Suppose you are going to roll a 6-face dice. What are chances to get an even number? It easy and it's 3/6 = 50%. Just before rolling the dice God knocked you and confirmed that **you will get a number greater than 3**. Now you have to re-calculate probability of getting an even number. How to do that ? What you think ? Will this condition increases probability ? Lets denote **"probability of getting an even number"** by **P(A)** and given condition **"you will get a number greater than 3"** by **P(B)**. We have to find out **P(A given B)**. Here is formula:

> **P(A given B) = P(A and B) / P(B)**

Lets verify above example:

> P(A and B) = 2 / 6 `[4, 6]`
> 
> P(B) = 3/6
> 
> P(A given B) = (2/6) / (3/6) = 2/3 = 67%
> 
> So when a condition is given probability will be increased


###### Dependent Probability:
As you see calculating probability of independent events, now it's time to think how about calculating probability of dependent outcomes. Please notice difference between independent events and dependent outcome and don't get confused by mixing this two things. Dependent outcomes mean there are some common portion of 2 different outcomes. Suppose when a dice is rolled what are chances to get a number which is even and greater than 3. Lets denote P(A) = **"probability of getting an even number"** and **"P(B) = probability of getting a number > 3"**. We have to find P(A and B). Here 2 outcomes have common portion which is **"probability of getting even number greater than 3"**. Basically we have to use same formula as used in conditional probability. Please notice benefit of conditional probability.

> **P(A and B) = P(A given B) . P(B) = P(B given A) . P(A)**


---

Now you can verify your solution of the example discussed above. Example 1 ~ 5.

###### Example 1~2:
I guess there's no need to explain solution. You are smart enough to solve these correctly.

###### Example 3:
Here is sample space when a dice rolled two times (at a time):

```
	1	2	3	4	5	6
1	2	3	4	5	6	7
2	3	4	5	6	7	8
3	4	5	6	7	8	9
4	5	6	7	8	9	10
5	6	7	8	9	10	11
6	7	8	9	10	11	12
```

###### Example 4:
Lets denote 

> **P(A) = "the probability that at least two people in the room have the same birthday." **
> 
> **P(A<sup>'</sup>) = "the probability that no two people have the same birthday."**
>
> **Then, P(A) = 1 - P(A<sup>'</sup>)**

It's easier to calculate P(A<sup>'</sup>) than P(A). that's why are gonna calculate calculate P(A<sup>'</sup>). We need to apply formula of probability of independent events.

Birthday of 1<sup>st</sup> friend could be any day of 365 days in a year. So probability is: 365/365 = 1

Birthday of 2<sup>nd</sup> friend could be any day of remaining 364 days in a year. So probability is: 364/365

Birthday of 3<sup>rd</sup> friend could be any day of remaining 363 days in a year. So probability is: 363/365

.....

Birthday of 23<sup>rd</sup> friend could be any day of remaining 343 days in a year. So probability is: 343/365

> P(A<sup>'</sup>) = (365/365) * (364/365) * (363/365) * (362/365) * .... * (343/365) = 0.492703
>
> So P(A) = 1 - P(A<sup>'</sup>) = 1 - 0.492703 = 0.507297 = 50.7297%

Lets solve this problem in another way. Probability of any two friends (one pair) have different birthday is = 1 - (1/365) = (364/365). Now from 23 friends total number of pairs = C(23, 2) = 252. Since any two pair have different birthday so probability of different birthday of these 252 pairs is = (364/365)<sup>252</sup>. Then if we subtract the value from 1 we will get our answer. Anyway this way we can make a general formula. If there are N number of friends and a year has D days then probability of any 2 of friends have different birthday is:

> **P(N) = 1 -  ((D-1)/D)<sup>C(N, 2)</sup>**


###### Example 5:
Give me some time to relax. The truth is I can't solve this problem except generating sample space ahtough this problem could be solved in several ways including conditional probability. You will find several solution in Wiki link given in problem description. I found this [MIT video lecture](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2010/video-lectures/lecture-18-probability-introduction/) which explains the problem by generating sample space. 

