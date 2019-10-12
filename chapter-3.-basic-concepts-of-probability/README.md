# Chapter 3. Basic Concepts of Probability

## 3.1 Sample Spaces, Events, and Their Probabilities

### 1\) Sample Spaces and Events

* _A_ **random experiment** _is a mechanism that produces a definite outcome that cannot be predicted with certainty. The_ **sample space** _associated with a random experiment is the set of all possible outcomes. An_ **event** _is a subset of the sample space._
* _An event_ _E_ _is said to_ **occur** _on a particular trial of the experiment if the outcome observed is an element of the set_ _E_.

**Example 1.** Construct a **sample space** for the experiment that consists of tossing a single coin.

**\[ Solution \]**    $$S = \{ H, T \}$$ 

**Exmaple 2.** Construct a **sample space** for the experiment that consists of rolling a single die. Find the **events** that correspond to the phrases “an even number is rolled” and “a number greater than two is rolled.”

**\[ Solution \]**    $$S = \{ 1, 2, 3, 4, 5, 6 \}$$ , $$S = \{ 2, 4, 6\}$$ ,  ****$$S = \{ 3, 4, 5, 6 \}$$ 



### 1-1\) Venn Diagram

 A graphical representation of a sample space and events is a **Venn diagram**

![Venn Diagram for Two Sample Spaces](https://saylordotorg.github.io/text_introductory-statistics/section_07/97b468eaa2da56c52e300c556c23a24f.jpg)

**Example 3.** A random experiment consists of **tossing two coins**.

1. Construct a sample space for the situation that the coins are indistinguishable, such as two brand new pennies.
2. Construct a sample space for the situation that the coins are distinguishable, such as one a penny and the other a nickel.

**\[ Solution \]**   

1. two same coins : two head -&gt; 2h, two tails -&gt; 2t, 2 different faces : d =&gt;$$S = \{ 2h, 2t, d \}$$ 
2. two different coins \(penny, nickel\) :  $$S = \{ hh, th, ht, tt\}$$



### 1-2\) Venn Diagram Plot in R

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
![](../.gitbook/assets/image%20%284%29.png)
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
![](../.gitbook/assets/image%20%287%29.png)
{% endtab %}

{% tab title="3-Set Diagram" %}
![](../.gitbook/assets/image%20%285%29.png)
{% endtab %}

{% tab title="4-set Diagram" %}
![](../.gitbook/assets/image%20%2813%29.png)
{% endtab %}
{% endtabs %}

\[ [source](http://www.incodom.kr/R_%28%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%EC%96%B8%EC%96%B4%29/VennDiagram) \]



