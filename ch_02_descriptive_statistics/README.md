# Chapter 2. Descriptive Statistics

### 2.1 Three Popular Data Displays

#### 1\) Stem and Leaf Diagrams

통계학 강의를 듣고 있는 30명 학생의 시험 성적은 다음과 같다.

```text
86 80 25 77 73  76 100 90 69 93
90 83 70 73 73  70  90 83 71 95
40 58 68 69 100 78  87 97 92 73
```

위의 데이터를 가시화하기 위한 방법 중 하나가 **stem and leaf diagram**이다.

R에서는 이러한 데이터 표현을 위해 `stem()` 함수를 사용한다.

**Syntax :**

```text
stem(x, scale = 1, width = 80, atom = 1e-08)
```

**arguments :**

* x : 수치형 벡터
* scale = : 플롯의 길이를 제어
* width = : 원하는 플롯의 넓이
* atom = : tolerance

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
score <- c(86, 80, 25, 77, 73,  76, 100, 90, 69, 93,
           90, 83, 70, 73, 73,  70,  90, 83, 71, 95,
           40, 58, 68, 69, 100, 78,  87, 97, 92, 73)
stem(score)
```
{% endtab %}

{% tab title="Result" %}
```text
##   The decimal point is 1 digit(s) to the right of the |
## 
##    2 | 5
##    3 | 
##    4 | 0
##    5 | 8
##    6 | 899
##    7 | 0013333678
##    8 | 03367
##    9 | 0002357
##   10 | 00
##
```
{% endtab %}
{% endtabs %}

10의 자리 숫자가 stem이 되고, 1의 자리 숫자가 leaf가 됨을 알 수 있다.

**연습문제**  stem의 갯수를 반으로 줄여서 diagram을 그려라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
stem(score, scale = 0.5)    # stem의 갯수를 50%로 줄임 -> 2, 4, 6, 8, 10 등
```
{% endtab %}

{% tab title="Result" %}
```text
##   The decimal point is 1 digit(s) to the right of the |
## 
##    2 | 5
##    4 | 08
##    6 | 8990013333678
##    8 | 033670002357
##   10 | 00
##
```
{% endtab %}
{% endtabs %}

#### 2\) Frequency Histograms

stem and leaf diagram은 대규모 데이터 세트에는 적합하지 않다.

이 때 사용되는 방법이 **빈도 히스토그램**이다.

```text
hist(x, main = paste("Histogram of ", xname), 
        xlim = range(breaks),
        ylim = NULL,
        xlab = xname, 
        ylab = 
        ... )
```

**arguments :**

* `x` : 히스토그램의 벡터 데이터
* `main =` : 히스토그램의 제목
* `xlim =` : x 축의 범위
* `ylim =` : y 축의 범위
* `xlab =` : x 축의 제목
* `ylab =` : y 축의 제목

이전의 stem and leaf diagram을 frequency histogram으로 그려라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
require(lattice)
require(openintro)

histogram(score, type = "count",
          xlim = c(0, 110),
          ylim = c(0, 12),
           breaks = seq(5, 105, by=10))
```
{% endtab %}

{% tab title="Result" %}
![](../.gitbook/assets/1570687481484.png)
{% endtab %}
{% endtabs %}

#### 3\) Relative Frequency Histogram

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
histogram(score, type = "percent",
          xlim = c(0, 110),
          ylim = c(0, 40),
          breaks = seq(5, 105, by=10))
```
{% endtab %}

{% tab title="Result" %}
 

![](../.gitbook/assets/1570687573652.png)
{% endtab %}
{% endtabs %}

y 축의 값이 갯수\(count\)가 아닌 백분율\(percent\)로 출력된다.

#### 4\) sample size and Relative Frequency Histograms

sample size가 커짐에 따라 전체 모양은 좌우 대칭의 종 모양이 된다.

![](../.gitbook/assets/1570687748413.png)

#### 5\) A Very Fine Relative Frequency Histogram

![](../.gitbook/assets/1570687965603.png)

### 2.2 Measures of Central Location

#### 1\) Mean

**Example 1\)** 다음 데이터 세트의 sum\(x\), sum\(x^2\), sum\( \(x-1\) ^2 \)을 구하시오.

```text
1 3 4
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1, 3, 4)
sum(x)
sum(x^2)
sum((x-1)^2)
```
{% endtab %}

{% tab title="Result" %}
```text
> sum(x)
## [1] 8
> sum(x^2)
## [1] 26
> sum((x-1)^2)
## [1] 13
```
{% endtab %}
{% endtabs %}

**Example 2\)** 다음의 표본 데이터의 평균을 구하라.

```text
2 -1 0  2
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c( 2, -1, 0, 2)
mean(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> mean(x)
## [1] 0.75
```
{% endtab %}
{% endtabs %}

**Example 3\)** 무작위로 선발한 10명의 학생의 평균 평점은 다음과 같다. 표본의 평균을 구하라.

```text
1.90 3.00 2.53 3.71 2.12 1.76 2.71 1.39 4.00 3.33
```

**\[풀이\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33)
mean(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> mean(x)
## [1] 2.645
```
{% endtab %}
{% endtabs %}

**Example 4\)** 가임기 년령을 넘긴 무작위로 선발된 19명의 여성의 데이터가 다음과 같다\(x는 자녀의 수, f는 그 값의 빈도\). 표본의 평균을 구하라.

```text
x   0   1   2   3   4
f   3   6   6   3   1
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(0, 1, 2, 3, 4)
f <- c(3, 6, 6, 3, 1)
mean <- sum(x * f) / sum(f)
mean
```
{% endtab %}

{% tab title="Result" %}
```text
> mean
## [1] 1.631579
```
{% endtab %}
{% endtabs %}

#### 2\) Median

기업 직원의 연 평균 수입에 관심이 있다고 가정하자. 무작위로 선발된 직원 7명의 대략적인 연 수입은 다음과 같다\(단위 : 천 달러\)

```text
24.8 22.8 24.6 192.4 25.2 18.5 23.7
```

* 소숫점 1자리에서 반올림한 평균 수입액을 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(24.8, 22.8, 24.6, 192.4, 25.2, 18.5, 23.7)
round(mean(x), 1)
```
{% endtab %}

{% tab title="Result" %}
```text
> round(mean(x), 1)
## [1] 47.4
```
{% endtab %}
{% endtabs %}

* 위의 계산으로 볼 때 192.4 데이터는 이상치\(outlier\)로 판단이 된다. 따라서 이 데이터의 중심값으로 평균값이 아닌 중앙값\(median\)을 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(24.8, 22.8, 24.6, 192.4, 25.2, 18.5, 23.7)
median(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> median(x)
## [1] 24.6
```
{% endtab %}
{% endtabs %}

**\[ Median \]**

![](../.gitbook/assets/1570693123203.png)

**Example 5\)** 다음 데이터 세트의 sample median을 구하라.

```text
-1 0 2 2
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(-1, 0, 2, 2)
median(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> median(x)
## [1] 1
```
{% endtab %}
{% endtabs %}

**Note :** median of the data set is the mean of 2nd and 3rd data -&gt; \(0 + 2\) / 2 = 1.

**Example 6\)** 다음 데이터 세트의 sample median을 구하라.

```text
1.39 1.76 1.90 2.12 2.53 2.71 3.00 3.33 3.71 4.00
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.39, 1.76, 1.90, 2.12, 2.53, 2.71, 3.00, 3.33, 3.71, 4.00)
median(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> median(x)
## [1] 2.62
```
{% endtab %}
{% endtabs %}

**Example 7\)** 다음 데이터 세트의 sample median을 구하라.

```text
0 0 0 1 1 1 1 1 1 2 2 2 2 2 2 3 3 3 4
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(0, 0, 0, 1, 1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 2, 3, 3, 3, 4)
median(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> median(x)
## [1] 2
```
{% endtab %}
{% endtabs %}

**\[ Skewness of Relative Frequency Histogram \]**

![](../.gitbook/assets/1570693694162.png)

#### 3\) The Mode

![](../.gitbook/assets/1570693777058.png)

**Example 8\)** 다음 데이터 세트의 mode\(최빈값\)를 구하라.

```text
-1 0 2 0
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(-1, 0, 2, 0)
y <- table(x)
names(which.max(y))
```
{% endtab %}

{% tab title="Result" %}
```text
> names(which.max(y))
## [1] "0"
```
{% endtab %}
{% endtabs %}

### 2.3 Measures of Variability

다음의 두 데이터 세트가 있다. 각각의 데이터 세트를 점으로 표현한 것이 dot plot이다.

| Data Set 1 | 40 | 38 | 42 | 40 | 39 | 39 | 43 | 40 | 39 | 40 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Data Set 2 | 46 | 37 | 40 | 33 | 42 | 36 | 40 | 47 | 34 | 45 |

{% tabs %}
{% tab title="R Code" %}
```text
library(ggplot2)
x1 <- c(40, 38, 42, 40, 39, 39, 43, 40, 39, 40)
x2 <- c(46, 37, 40, 33, 42, 36, 40, 47, 34, 45)
x <- data.frame(x1, x2)

ggplot(x, aes(x = x1)) + geom_dotplot()
ggplot(x, aes(x = x2)) + geom_dotplot()
```
{% endtab %}

{% tab title="Result 1" %}
  

![](../.gitbook/assets/1570695168698.png)
{% endtab %}

{% tab title="Result 2" %}
![](../.gitbook/assets/1570695188616.png)
{% endtab %}
{% endtabs %}

참고사이트 : [https://ggplot2.tidyverse.org/reference/geom\_dotplot.html](https://ggplot2.tidyverse.org/reference/geom_dotplot.html)

#### 1\) The Range

**Example 9\)** 앞의 2개의 데이터 세트의 range를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x1 <- c(40, 38, 42, 40, 39, 39, 43, 40, 39, 40)
x2 <- c(46, 37, 40, 33, 42, 36, 40, 47, 34, 45)
range_x1 <- max(x1) - min(x1)
range_x2 <- max(x2) - min(x2)
```
{% endtab %}

{% tab title="Result" %}
```text
> ( range_x1 <- max(x1) - min(x1) )
## [1] 5
> ( range_x2 <- max(x2) - min(x2) )
## [1] 14
```
{% endtab %}
{% endtabs %}

**Note :** `range( )`function of R displays the minimun value and the maxim value of the data set.

#### 2\) The Variance and The Standard Deviation

**Example 10\)** Data Set 2의 sample variance와 sample standard deviation을 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x2 <- c(46, 37, 40, 33, 42, 36, 40, 47, 34, 45)
var(x2)
sd(x2)
```
{% endtab %}

{% tab title="Result" %}
```text
> var(x2)
## [1] 24.88889
> sd(x2)
## [1] 4.988877
```
{% endtab %}
{% endtabs %}

**Example 11\)** 무작위로 선발한 10명의 학생의 평균 평점은 다음과 같다. sample variance와 sample standard deviation을 구하라.

```text
1.90 3.00 2.53 3.71 2.12 1.76 2.71 1.39 4.00 3.33
```

**\[풀이\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33)
var(x)
sd(x)
```
{% endtab %}

{% tab title="Result" %}
```text
> var(x)
## [1] 0.7524278
> sd(x)
## [1] 0.8674259
```
{% endtab %}
{% endtabs %}

**\[ Difference between Two Data Sets \]**

![](../.gitbook/assets/1570696359581.png)

### 2.4 Relative Position of Data

#### 1\) Percentiles and Quartiles

* Given an observed value x in a data set, x is the Pth **percentile** of the data if the percentage of the data that are less than or equal to x is P. The number P is the percentile rank of x.

**Example 12\)** Example 3\)의 데이터 세트에 대하여 1.39의 percentile을 구하라. 3.33의 percentile도 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33)

length(x[x <= 1.39]) / length(x) * 100
length(x[x <= 3.33]) / length(x) * 100
```
{% endtab %}

{% tab title="Result 1" %}
```text
> length(x[x <= 1.39]) / length(x) * 100
## [1] 10
```
{% endtab %}

{% tab title="Result 2" %}
```text
> length(x[x <= 3.33]) / length(x) * 100
## [1] 80
```
{% endtab %}
{% endtabs %}

\[ Data Division by Quartiles\]

![](../.gitbook/assets/20191011_102919.png)

For any data set: 

1. The **second quartile** Q2 of the data set is its median. 

2. Define two subsets: 

* the lower set: all observations that are strictly less than Q2; 
* the upper set: all observations that are strictly greater than Q2. 

3. The **first quartile** Q1 of the data set is the median of the lower set.

**Example 13\)** 앞의 예에 있는 데이터 세트의 quartiles를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33)
y <- quantile(x)
y                # quartiles of x
y[3]             # second quartile of x
sort(x[x<y[3]])  # lower subset
sort(x[x>y[3]])  # upper subset
```
{% endtab %}

{% tab title="quartiles" %}
```text
> y
##     0%    25%    50%    75%   100% 
## 1.3900 1.9550 2.6200 3.2475 4.0000 
```
{% endtab %}

{% tab title="lower subset" %}
```text
> sort(x[x<y[3]])  # lower subset
## [1] 1.39 1.76 1.90 2.12 2.53
```
{% endtab %}

{% tab title="upper subset" %}
```text
> sort(x[x>y[3]])  # upper subset
## [1] 2.71 3.00 3.33 3.71 4.00
```
{% endtab %}
{% endtabs %}

**Example 14\)** 앞의 데이터 세트에 3.88을 추가하고 quartiles를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33, 3.88)
y <- quantile(x)
y                # quartiles of x
y[3]             # second quartile of x
sort(x[x<y[3]])  # lower subset
sort(x[x>y[3]])  # upper subset
```
{% endtab %}

{% tab title="quartiles" %}
```text
> y
##   0%  25%  50%  75% 100% 
## 1.39 2.01 2.71 3.52 4.00 
```
{% endtab %}

{% tab title="lower subset" %}
```text
> sort(x[x<y[3]])  # lower subset
## [1] 1.39 1.76 1.90 2.12 2.53
```
{% endtab %}

{% tab title="upper subset" %}
```text
> sort(x[x>y[3]])  # upper subset
## [1] 3.00 3.33 3.71 3.88 4.00
```
{% endtab %}
{% endtabs %}

* **five-number summary** of the data set:

```text
{xmin, Q1, Q2, Q3, xmax}
```

* The five-number summary is used to construct a **box plot.**

![](../.gitbook/assets/20191011_105716.png)

#### 2\) IQR

* **The interquartile range \(IQR\)** is the quantity : 

```text
 IQR = Q3−Q1 
```

**EXAMPLE 15\)** Example 13\)의 Box Plot을 작성하라. 그리고 IQR을를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33)
boxplot(x)
quantile(x)
IQR(x)
```
{% endtab %}

{% tab title="Box Plot" %}
![](../.gitbook/assets/image%20%2816%29.png)
{% endtab %}

{% tab title="IQR" %}
```text
> quantile(x)
##     0%    25%    50%    75%   100% 
## 1.3900 1.9550 2.6200 3.2475 4.0000 
> IQR(x)
## [1] 1.2925
```
{% endtab %}
{% endtabs %}

* The **z-score** of an observation x is the number of z given by the computational formula

 $$z =  (x - x^-)  /  {\delta} $$      or       $$z = (x - \mu) / \sigma$$ 

according to whether the data set is a sample or is the entire population.

* x-scale vs z-scale

![](../.gitbook/assets/image%20%287%29.png)

**Example 16\)** 다음과 같은 10명의 학생의 평균 평점에 대하여 z-score를 구하라.

```text
1.90 3.00 2.53 3.71 2.12 1.76 2.71 1.39 4.00 3.33
```

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(1.90, 3.00, 2.53, 3.71, 2.12, 1.76, 2.71, 1.39, 4.00, 3.33)
z_score <- (x - mean(x)) / sd(x)
round(z_score, 2)
```
{% endtab %}

{% tab title="z-score" %}
```text
> round(z_score, 2)
##  [1] -0.86  0.41 -0.13  1.23 -0.61 -1.02  0.07 -1.45  1.56  0.79
```
{% endtab %}
{% endtabs %}

**Example 17\)** 최근에 등록했던 학생들 평균 평점의 평균과 표준편차가 각각 $$\mu = 2.70$$과 $$\sigma = 0.50$$ 이었다. Antonio와 Beatrice 두 학생의 z-score는 각각 -0.62와 1.28이었다. 그들의 평균 평점은 몇 점인가?

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
mean <- 2.70
std <- 0.50
z_score <- c(-0.62, 1.28)
GPA <- mean + std * z_score
```
{% endtab %}

{% tab title="z-score" %}
```text
> GPA <- mean + std * z_score; GPA
## [1] 2.39 3.34
```
{% endtab %}
{% endtabs %}

### 2.5 The Empirical Rule and Chebychev's Theorem

You probably have a good intuitive grasp of what the **average of a data set** says about that data set. In this section we begin to learn what the **standard deviation** has to tell us about the nature of the data set.

#### 1\) Empirical Rule

성인 남성 100명의 키\(인치 단위\)에 대한 데이터 세트가 있다.

![Heights of Men](../.gitbook/assets/image.png)

![Relative Frequency Histogram of Heights of Adult Men](../.gitbook/assets/image%20%2829%29.png)

**The Empirical Rule** 

If a data set has an _approximately bell-shaped relative frequency histogram_, then \(see Figure 2.16 "The Empirical Rule"\) 

1. approximately 68% of the data lie within one standard deviation of the mean, that is, in the interval with endpoints $$x^−$$ ± 1s for samples and with endpoints μ ± 1σ for populations; 

2. approximately 95% of the data lie within two standard deviations of the mean, that is, in the interval with endpoints $$x^−$$ ± 2s for samples and with endpoints μ ± 2σ for populations; and 

3. approximately 99.7% of the data lies within three standard deviations of the mean, that is, in the interval with endpoints $$x^-$$  ± 3s for samples and with endpoints μ ± 3σ for populations.

![](../.gitbook/assets/image%20%2832%29.png)

Two key points in regard to the Empirical Rule are that the data distribution must be _**approximately bell-shaped**_ and that the percentages are only _**approximately**_ true.

**Example 18\)** 18세 남성들의 키가 평균 69.6 인치, 표준편차 1.4 인치의 종모양 분포를 한다. 

a\) 이 사람들 중에 몇 퍼센트가 68.2인치와 71인치 사이에 있을까?

b\) 이 사람들 중에 95% 정도가 포함되는 평균의 구간을 구하라.

**\[Solution a\]**

{% tabs %}
{% tab title="R Code" %}
```text
mean <- 69.6
std <- 1.4
x <- (68.2, 71)
z <- (x - mean) / std
```
{% endtab %}

{% tab title="Result a\)" %}
```text
> z
## [1] -1  1
```
{% endtab %}
{% endtabs %}

**\[Solution b\]**

{% tabs %}
{% tab title="R Code" %}
```text
mean <- 69.6
std <- 1.4
z <- 2
x1 <- mean + z * std; x1
x2 <- mean - z * std; x2
```
{% endtab %}

{% tab title="Result b\)" %}
```text
> x1 <- mean + z * std; x1
## [1] 72.4
> x2 <- mean - z * std; x2
## [1] 66.8
```
{% endtab %}
{% endtabs %}

![](../.gitbook/assets/image%20%2828%29.png)

**Example 19\)** IQ 테스트 점수가 $$\mu = 100$$ 이고, $$\sigma = 10$$ 을 가진 종모양의 분포를 한다. 110, 120, 130 의 IQ를 가진 개인들과 관련하여 어떤 Empirical Rule이 적용되는가?

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
mean <- 100
std <- 10
x <- c(110, 120, 130)
z <- (x - mean) / std ; z
```
{% endtab %}

{% tab title="z-scores" %}
```text
> z <- (x - mean) / std ; z
## [1] 1 2 3
```
{% endtab %}
{% endtabs %}

![Distribution of IQ Scores](../.gitbook/assets/image%20%2823%29.png)

#### 2\) Chebychev's Theorem

For any numerical data set, 

1. at least $$3 / 4$$ of the data lie within two standard deviations of the mean, that is, in the interval with endpoints \($$x^-  $$ ±  2s\) for samples and with endpoints \(μ ± 2σ\) for populations; 
2. at least 8/9 of the data lie within three standard deviations of the mean, that is, in the interval with endpoints  \($$x^-  $$ ± 3s\) for samples and with endpoints \(μ ± 3σ\) for populations;
3. at least $$(1 - 1/k^2)$$ of the data lie within k standard deviations of the mean, that is, in the interval with endpoints \($$x^-  $$± ks\) for samples and with endpoints \(μ ± kσ\) for populations, where k is any positive whole number that is greater than 1.

![A visual illustration of Chebchev&apos;s Theorem](../.gitbook/assets/image%20%2817%29.png)

It is important to pay careful attention to the words “at least” at the beginning of each of the three parts. The theorem gives _the minimum proportion of the data_ which must lie within a given number of standard deviations of the mean; the true proportions found within the indicated regions could be greater than what the theorem guarantees.

**Example 20\)** 표본의 크기 $$n = 50$$인 표본이 평균 $$x^- = 28$$ , 그리고 표준편차 $$s = 3$$를 갖는다. 표본에 대한 어떠한 정보도 없이, \(22, 34\) 구간에 얼마나 많은 관측 데이터가 있을 수 있는가? 그리고 이 구간 밖에는 얼마나 많은 관측 데이터가 있다고 말할 수 있는가?

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
mean <- 28
std <- 3
x <- c(22, 34)
z <- (x - mean) / std ; z
```
{% endtab %}

{% tab title="z-score" %}

{% endtab %}
{% endtabs %}

![](../.gitbook/assets/image%20%2833%29.png)

**Example 21\)** 작년 매일 평일 오전 8시에서 10시 사이에 혼잡한 교차로를 통과하는 차량의 수를 관찰하여 기록하였다. 이 데이터 세트는 규모가 $$n = 251$$ 이다. 표본평균 $$x^- = 725$$ 이고, 표준편차 $$s = 25$$ 이다. 다음 중 사실인 것을 찾아라.

1. On approximately 95% of the weekday mornings last year the number of vehicles passing through the intersection from 8:00 a.m. to 10:00 a.m. was between 675 and 775.
2. On at least 75% of the weekday mornings last year the number of vehicles passing through the intersection from 8:00 a.m. to 10:00 a.m. was between 675 and 775.
3. On at least 189 weekday mornings last year the number of vehicles passing through the intersection from 8:00 a.m. to 10:00 a.m. was between 675 and 775. 
4. On at most 25% of the weekday mornings last year the number of vehicles passing through the intersection from 8:00 a.m. to 10:00 a.m. was either less than 675 or greater than 775. 
5. On at most 12.5% of the weekday mornings last year the number of vehicles passing through the intersection from 8:00 a.m. to 10:00 a.m. was less than 675. 
6. On at most 25% of the weekday mornings last year the number of vehicles passing through the intersection from 8:00 a.m. to 10:00 a.m. was less than 675.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
mean <- 725
std <- 25
x <- c(675, 775)
z <- (x - mean) / std ; z
```
{% endtab %}

{% tab title="z-score" %}
```text
> z <- (x - mean) / std ; z
## [1] -2  2
```
{% endtab %}
{% endtabs %}

1. 데이터의 relative frequency histogram이 종모양인지 언급이 없기 때문에 Empirical Rule이 적용되지 않는다. 따라서 \(1\)번 문장은 맞지 않을 수 있다.
2. chebychev's theorem이 적용되어 이 문장은 맞다.
3. 189/251 = 75.3% 그러므로 이 문장은 \(2\)번 문장과 같다. 따라서 이 문장도 맞는다..
4. 이 문장은 \(2\)번 문장과 같다. 따라서 이 문장도 맞는다.
5. \(4\)번 문장은 사실이다. 그러나 \(5\)번 문장은 relative frequency histogram이 대칭적\(symmetric\)인지 여부를 알 수 없기 때문에 이 문장이 맞다고 말할 수 없다. 즉,  relative frequency histogram 이 대칭적이라면 이 문장은 맞는다.
6. 이 문장은 \(4\)번 문장과 같다. 따라서 이 문장도 맞는다.

