# Chapter 1. Introduction

## 1.1 기본 정의 및 개념

* A **population\(모집단\)** is any specific collection of objects of interest. A sample is any subset or subcollection of the population, including the case that the sample consists of the whole population, in which case it is termed a census.
* A **measurement\(측정치\)** is a number or attribute computed for each member of a population or of a sample. The measurements of sample elements are collectively called the sample data.
* A **parameter\(모수\)** is a number that summarizes some aspect of the population as a whole. A statistic is a number computed from the sample data.
* **Statistics** is a collection of methods for collecting, displaying, analyzing, and drawing conclusions from data.
* **Descriptive statistics** is the branch of statistics that involves organizing, displaying, and describing data.
* **Inferential statistics** is the branch of statistics that involves drawing conclusions about a population based on information contained in a sample taken from that population.
* **Qualitative data** are measurements for which there is no natural numerical scale, but which consist of attributes, labels, or other nonnumerical characteristics.
* **Quantitative data** are numerical measurements that arise from a natural numerical scale.

![Grand Picture of Statistics](../.gitbook/assets/20191010_130523.png)

## 1.2 Overview

* The **sample average** is an example of what is called a **random variable**: a number that varies from trial to trial of an experiment \(in this case, from sample to sample\), and does so in a way that cannot be predicted precisely.
* A different samples have different **levels of reliability**.
* Single estimation
* The **confidence interval**: from the data we will construct an interval of values so that the process has a certain chance, say a 95% chance, of generating an interval that contains the actual population average.
* **probability**
* **Sampling**
* ...

## 1.3 Presentation of Data

**Example 1.** 임의로 선택된 21명 학생들의 나이 데이터이다. 이들 데이터에 대한 도수 분포표를 작성하라.

```text
18 18 19 19 19 18 22 20 18 18 17 19 18 24 18 20 18 21 20 17 19
```

{% tabs %}
{% tab title="R Code" %}
```text
age <- c(18, 18, 19, 19, 19, 18, 22, 20, 18, 18, 17, 19, 18, 24, 18, 20, 18, 21, 20, 17, 19)# 1. Frequency Tabley <- table(age) ; y# 2. Relative Frequency Tableprop.table(y)# 3. Frequency Diagramplot(y)# 4. Relative Frequency Diagramplot(prop.table(y))
```
{% endtab %}

{% tab title="Frequency Table" %}
```text
> # 1. Frequency Table> y <- table(age); y## age## 17 18 19 20 21 22 24 ##  2  8  5  3  1  1  1 >> # 2. Relative Frequency Table> prop.table(y)## age##         17         18         19         20         21         22         24 ## 0.09523810 0.38095238 0.23809524 0.14285714 0.04761905 0.04761905 0.04761905 > 
```
{% endtab %}

{% tab title="Plot" %}
* Frequency Diagram

![](../.gitbook/assets/image%20%28156%29.png)

* Relative Frequency Diagram

![](../.gitbook/assets/image%20%2819%29.png)
{% endtab %}
{% endtabs %}

위의 데이터 세트에 대한 **도수 분포표\(frequency table\)**가 작성되었다. 이 표에는 x 의 유일값이 첫 번째 행에 나열이 되고, 두번째 행에는 데이터 세트에 나타나는 x 값의 빈도\(frequency\) f 값이 출력된다.

