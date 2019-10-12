# Chapter 3. Basic Concepts of Probability

## 3.1 Sample Spaces, Events, and Their Probabilities

### 1\) Sample Spaces and Events

* _A_ **random experiment** _is a mechanism that produces a definite outcome that cannot be predicted with certainty. The_ **sample space** _associated with a random experiment is the set of all possible outcomes. An_ **event** _is a subset of the sample space._
* _An event_ _E_ _is said to_ **occur** _on a particular trial of the experiment if the outcome observed is an element of the set_ _E_.

**Example 1.** Construct a **sample space** for the experiment that consists of tossing a single coin.

**\[ Solution \]**    $$S = \{ H, T \}$$ 

**Exmaple 2.** Construct a **sample space** for the experiment that consists of rolling a single die. Find the **events** that correspond to the phrases “an even number is rolled” and “a number greater than two is rolled.”

**\[ Solution \]**    $$S = \{ 1, 2, 3, 4, 5, 6 \}$$ , $$S = \{ 2, 4, 6\}$$ ,  ****$$S = \{ 3, 4, 5, 6 \}$$ 



#### 1-1\) Venn Diagram

 A graphical representation of a sample space and events is a **Venn diagram**

![Venn Diagram for Two Sample Spaces](https://saylordotorg.github.io/text_introductory-statistics/section_07/97b468eaa2da56c52e300c556c23a24f.jpg)

**Example 3.** A random experiment consists of **tossing two coins**.

1. Construct a sample space for the situation that the coins are indistinguishable, such as two brand new pennies.
2. Construct a sample space for the situation that the coins are distinguishable, such as one a penny and the other a nickel.

**\[ Solution \]**   

1. two same coins : two head -&gt; 2h, two tails -&gt; 2t, 2 different faces : d =&gt;$$S = \{ 2h, 2t, d \}$$ 
2. two different coins \(penny, nickel\) :  $$S = \{ hh, th, ht, tt\}$$

#### 1-2\) Venn Diagram Plot in R

* type of count data.

```text
A   450
B   1800
A and B both    230
```

I want to develop a colorful \(possibly semi-transparency at intersections\) like the following Venn diagram.

{% tabs %}
{% tab title="R Code" %}
```text
require(venneuler)
v <- venneuler(c(A=450, B=1800, "A&B"=230))
plot(v)
```
{% endtab %}

{% tab title="Venn Diagram" %}
![](../.gitbook/assets/image%20%287%29.png)
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="R Code" %}
```text
# install package
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("VennDiagram")
library("VennDiagram")

# 2-set diagram
venn.plot <- draw.pairwise.venn(30, 20, 10, c("A-up", "B-up"), scaled = FALSE);

venn.plot <- draw.triple.venn(
  area1 = 60,
  area2 = 70,
  area3 = 80,
  n12 = 30,
  n23 = 20,
  n13 = 10,
  n123 = 5,
  category = c("A_up-regulation", "B_up-regulation", "C_up-  regulation"),
);

# 3-set diagram
venn.plot <- draw.triple.venn(
  area1 = 60,
  area2 = 70,
  area3 = 80,
  n12 = 30,
  n23 = 20,
  n13 = 10,
  n123 = 5,
  category = c("A_up-regulation", "B_up-regulation", "C_up-  regulation"),
);

# 4-set diagram
venn.plot <- draw.quad.venn(
  area1 = 90,
  area2 = 80,
  area3 = 75,
  area4 = 49,
  n12 = 37,
  n13 = 25,
  n14 = 26,
  n23 = 34,
  n24 = 30,
  n34 = 22,
  n123 = 16,
  n124 = 15,
  n134 = 10,
  n234 = 12,
  n1234 = 3,
  category = c("First", "Second", "Third", "Fourth"),
  fill = c("orange", "red", "green", "blue"),
  lty = "dashed",
  cex = 2,
  cat.cex=2,
  cat.col = c("orange", "red", "green", "blue")
);
```
{% endtab %}

{% tab title="2-Set Diagram" %}
![](../.gitbook/assets/image%20%2811%29.png)
{% endtab %}

{% tab title="3-Set Diagram" %}
![](../.gitbook/assets/image%20%289%29.png)
{% endtab %}

{% tab title="4-set Diagram" %}
![](../.gitbook/assets/image%20%2818%29.png)
{% endtab %}
{% endtabs %}

\[ [source](http://www.incodom.kr/R_%28%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%EC%96%B8%EC%96%B4%29/VennDiagram) \]

#### 1-3\) tree diagram

*  A device that can be helpful in identifying all possible outcomes of a random experiment, particularly one that can be viewed as proceeding in stages, is what is called a **tree diagram**.

**Example 4.** Construct a sample space that describes all three-child families according to the genders of the children with respect to birth order.

**\[ Solution \]** $$S = \{ bbb, bbg, bgb, bgg, gbb, gbg, ggb, ggg \}$$ , g=girl ; b=boy

![](https://saylordotorg.github.io/text_introductory-statistics/section_07/e9de1d9b1c09ed5a0870567d7e5ad809.jpg)

The line segments are called **branches** of the tree. The right ending point of each branch is called a **node**. The nodes on the extreme right are the **final nodes**; to each one there corresponds an outcome, as shown in the figure.

#### **1-4\) Tree Diagram in R**

* [fancyRpartPlot in R](http://www.dodomira.com/2016/07/19/r-%EC%9D%98%EC%82%AC%EA%B2%B0%EC%A0%95%EB%82%98%EB%AC%B4-%EA%B9%94%EB%81%94%ED%95%98%EA%B2%8C-plotting-%ED%95%98%EA%B8%B0-fancyrpartplot-r/)

![](../.gitbook/assets/image%20%284%29.png)

* \*\*\*\*[How to create a massive tree diagram in RStudio?](https://stackoverflow.com/questions/36206299/how-to-create-a-massive-tree-diagram-in-rstudio)

![](../.gitbook/assets/image%20%2820%29.png)

* [Introduction to data.tree](https://cran.r-project.org/web/packages/data.tree/vignettes/data.tree.html)

![](../.gitbook/assets/image%20%2819%29.png)

![](../.gitbook/assets/image%20%2821%29.png)

* [PROBABILITY TREE DIAGRAMS IN R](http://www.harrysurden.com/wordpress/archives/292)

![](../.gitbook/assets/image%20%2814%29.png)

![](../.gitbook/assets/image%20%288%29.png)

### 2\) Probability

* _The_ **probability of an outcome** _**e**_ _in a sample space_ _S_ _is a number_ _p_ _between 0 and 1 that measures the likelihood that_ _e_ _will occur on a single trial of the corresponding random experiment. The value_ $$p = 0$$ _corresponds to the outcome_ _e_ _being impossible and the value_ $$p = 1$$ _corresponds to the outcome_ _e_ _being certain._
*  _he_ probability of an event _A_ _is the sum of the probabilities of the individual outcomes of which it is composed. It is denoted_  $$p(A)$$. 

If an event $$E $$ is $$E = \{e_1, e_2,  ..., e_k \}$$, then

                                         $$P(E)=P(e_1)+P(e_2)+ ⋅ ⋅ ⋅ +P(e_k)$$   


![Sample Space and Probability](https://saylordotorg.github.io/text_introductory-statistics/section_07/b1371037e2e863e76e91bc00adf37f63.jpg)

**Example 5.** A coin is called “balanced” or “fair” if each side is equally likely to land up. Assign a probability to each outcome in the sample space for the experiment that consists of tossing a single fair coin.

**\[ Solution \]** $$S = \{ H, T \}$$ ,         $$p(H) = p(T) =1/2$$ 

**Example 6.** A die is called “balanced” or “fair” if each side is equally likely to land on top. Assign a probability to each outcome in the sample space for the experiment that consists of tossing a single fair die. Find the probabilities of the events _E_: “an even number is rolled” and _T_: “a number greater than two is rolled.”

**\[ Solution \]**  $$S = \{ 1, 2, 3, 4, 5, 6 \}$$\*\*\*\*

1. $$E = \{ 2, 4, 6\}$$ ,  $$p(E) = 3 / 6 = 1/2$$ 
2. $$T = \{3, 4, 5, 6 \}$$ , $$P(T) = 4/6 = 2/3$$ 

**Example 7.** Two fair coins are tossed. Find the probability that the coins match, i.e., either both land heads or both land tails.

**\[ Solution \]**

1. identical coins **:** $$S = \{ 2h, 2t, d \}$$ , $$E = \{2h, 2t \} $$ =&gt;  $$P(E)   = 2/3$$ 
2. two different coins : $$S^t = \{ 2h, ht, th, 2t  \}$$ , $$E^t = \{2h, 2t \} $$ =&gt; $$p(E^t) = 2/4 = 1/2$$ 

**Example 8.** The breakdown of the student body in a local high school according to race and ethnicity is 51% white, 27% black, 11% Hispanic, 6% Asian, and 5% for all others. A student is randomly selected from this high school. \(To select “randomly” means that every student has the same chance of being selected.\) Find the probabilities of the following events:

![](../.gitbook/assets/image%20%282%29.png)

1. _B_: the student is black,
2. _M_: the student is minority \(that is, not white\),
3. _N_: the student is not black.

**\[ Solution \]**

1. $$P(B) = P(b) = 0.27$$ 
2. $$P(M) = 1 - P(w) = 1 - 0.51 = 0.49$$ 
3. $$P(N) = 1 - P(b) = 1-0.27 = 0.73$$ 

**Example 9.** The student body in the high school considered in "**Example 8**" may be broken down into ten categories as follows: 25% white male, 26% white female, 12% black male, 15% black female, 6% Hispanic male, 5% Hispanic female, 3% Asian male, 3% Asian female, 1% male of other minorities combined, and 4% female of other minorities combined. A student is randomly selected from this high school. Find the probabilities of the following events:

![](../.gitbook/assets/image%20%281%29.png)

1. $$B$$ : the student is black,
2. $$MF$$ : the student is minority female,
3. $$FN$$ : the student is female and is not black.

**\[ Solution \]**

1. $$P(B) = P(bm) + P(bf) = 0.12 + 0.15 = 0.27$$ ****
2. $$P(MF) = P(bf) + P(hf) + P(af) + P(of)  = 0.15 +0.05+0.03+0.04=0.27$$ 
3. $$P(FN) = P(wf) + P(hf) + P(af) + P(of) = 0.26 +0.05+0.03+0.04 = 0.38$$ 

\*\*\*\*
