# 2-3. Exercises

### 1\) Basic Exercises

**Ex 1.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
1 2 3 4
```

**Ex 2.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
2 -2 6 0 2 1
```

**Ex 3.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
2 1 2 7
```

**Ex 4.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
-1 0 1 4 1 1
```

**Ex 5.** data frequency table로 표현된 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
x  1 2 7
f  1 2 1
```

**Ex 6.** data frequency table로 표현된 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
x  -1 0 1 4
f   1 1 2 1
```



### 2\) Applications Exercies

**Ex 7.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
122 162 123 145 148 120 147 160 150 152
```

**Ex 8.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
142 152 128 145 148 129 147 155 150 152
```



### 3\) Additional Exercises

**Ex 9.** 다음의 표로 나타난 데이터 세트가 있다.

```text
x 26 27 28 29 30 31 32
f  3  4 16 12  6  2  1
```

a. 이 표를 이용하여 $$\Sigma x$$ 와 $$\Sigma x^2$$ 을 구하라.

b. 위의 결과를 이용하여 표본 평균과 표본 표준편차를 구하라. 



**Ex 10.** 다음의 데이터에 대하여 표본 표준편차를 구하라.

```text
x    1    2    3    4    5    6    7    8    9   10
f  284  208   98   56   28   12    8    2    3    1
```



**Ex 11.** 자동차 수리센터에서 수리비 청서를 49건 무작위로 선택하였다. 그 데이터를 stem and leaf diagram으로 정렬하였다. \(stem은 천단위, leaf는 백단위로 표시되어 있으며  가장 큰 금액은 3,800이었다.\)

```text
  0 | 4
  0 | 5688
  1 | 0012444
  1 | 55566777889
  2 | 000001224
  2 | 566778899
  3 | 001124
  3 | 568
```

a. 평균, 중앙값 그리고 최빈값을 구하라.

b. 범위\(range\)를 구하라.

c. 표본 표준편차를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(35, 36, 38, 30, 30, 31, 31, 32, 34, 25, 26, 26, 27, 27, 28, 28, 
       29, 29, 20, 20, 20, 20, 20, 21, 22, 22, 24, 15, 15, 15, 16, 16,
       17, 17, 17, 18, 18, 19, 10, 10, 11, 12, 14, 14, 14, 5, 6, 8, 8,
        4)
stem(x)

# a.
mean(x)   # mean
median(x) # median
y <- table(x)   # mode
names(which.max(y))

# b.
range <- max(x) - min(x); range

# c.
sd(x)
```
{% endtab %}

{% tab title="a." %}
```text
> # a.
> mean(x)   # mean
[1] 20.6
```
{% endtab %}

{% tab title="b." %}
```text
> median(x) # median
[1] 20
```
{% endtab %}

{% tab title="c." %}
```text
> y <- table(x)   # mode
> names(which.max(y))
[1] "20"
```
{% endtab %}
{% endtabs %}

**Ex 12.** 표준 편차가 0인 데이터 세트의 특징에 대하여 서술하라.

**Ex 13.** 25개의 측정치로 구성된 데이터 세트의 표준편차가 0이다. 이 측정치 중의 하나가 17의 값을 가지고 있다. 나머지 24개 측정치는 어떻게 구성이 되는가?

**Ex 14.** 범위의 값이 0이고, 표본 평균이 2이 는 표본의 크기가 3인 데이터 세트를 작성하라.

**Ex 15.** 표본 분산 값이 0이고, 표본 평균이 1이 되는 표본 크기 3의 데이터 세트를 작성하라.

**Ex 16.** \(-1, 0, 1\) 표본은 평균이 0, 표준편차가 1이다. 평균이 0이고 표준편차가 1보다 더 큰 값을 갖는 표본 크기 3인 데이터 세트를 작성하라.

**Ex 17.** \(-1, 0, 1\) 표본은 평균이 0, 표준편차가 1이다. 평균이 0이고 표준편차가 1보다 더 작은큰 값을 갖는 표본 크기 3인 데이터 세트를 작성하라.

**Ex 18.** 다음과 같은 데이터 세트가 있다. 이 데이터 세트를 Data Set 1이라고 하자.

```text
5 -2 6 14 -3 0 1 4 3 3 5
```

a. Data Set 1의 표본 표준편차를 구하라.

b. 이 Data Set 1의 각 수치에 3을 더하여 Data Set II를 작성하라. 그리고 이 Data Set II의 표본 표준편차를 구하라.

c. Data Set I의 각 수치에서 6을 뺀 값으로 구성된 Data Set III를 작성하라. 그리고 이 Data Set III의 표본 표준편차를 구하라.

d. \(a\), \(b\), \(c\)의 결과를 비교하고 일반적인 원리로 제시할 수 있는 패턴을 설명하라. 

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
ds1 <- c(5, -2, 6, 14, -3, 0, 1, 4, 3, 3, 5)

# a
sd(ds1)

# b
ds2 <- ds1 + 3; ds2
sd(ds2)

# c
ds3 <- ds2 - 6; ds3
sd(ds3)
```
{% endtab %}

{% tab title="a" %}
```text
> # a
> sd(ds1)
[1] 4.60632
```
{% endtab %}

{% tab title="b" %}
```text
> # b
> ds2 <- ds1 + 3; ds2
 [1]  8  1  9 17  0  3  4  7  6  6  8
> sd(ds2)
[1] 4.60632
```
{% endtab %}

{% tab title="c" %}
```text
> # c
> ds3 <- ds2 - 6; ds3
 [1]  2 -5  3 11 -6 -3 -2  1  0  0  2
> sd(ds3)
[1] 4.60632
```
{% endtab %}

{% tab title="d" %}
\(a\), \(b\), \(c\) have the same standard deviation. 

=&gt; sd\(x\) = sd\(x + a\) = sd\(x - a\)
{% endtab %}
{% endtabs %}

**Ex 19.** 1,000 명의 학생들의 SAT와 GPS 성적을 수록하고 있는 Data Set 1이 의 사이트에 수록되어 있다.

 [http://www.flatworldknowledge.com/sites/all/files/data1.xls](http://www.flatworldknowledge.com/sites/all/files/data7A.xls) 

a. SAT 성적의 범위와 표본 표준편차를 구하라.

b. GPS 성적의 범위와 표본 표준편차를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
install.packages("readxl")
library(readxl)

dataset1 <- read_excel("data1.xls")
str(dataset1)

# a.
range_SAT <- max(dataset1[[1]]) - min(dataset1[[1]])
range_SAT
sd(dataset1[[1]])

# b.
range_GPA <- max(dataset1[[2]]) - min(dataset1[[2]])
range_GPA
sd(dataset1[[2]])
```
{% endtab %}

{% tab title="Data Set 1" %}
```text
> str(dataset1)                                                                                                                > str(dataset1)
Classes ‘tbl_df’, ‘tbl’ and 'data.frame':   1000 obs. of  2 variables:
 $ SAT Score  : num  1300 1520 1580 1430 1610 1230 1520 1320 1240 1480 ...
 $ College GPA: num  3.66 2.92 2.66 2.27 2.35 2.02 2.94 1.76 2.35 3.16 ...
>
```
{% endtab %}

{% tab title="a" %}
```text
> # a.
> range_SAT <- max(dataset1[[1]]) - min(dataset1[[1]])
> range_SAT
[1] 1350
> sd(dataset1[[1]])
[1] 212.5455
```
{% endtab %}

{% tab title="b" %}
```text
> # b.
> range_GPA <- max(dataset1[[2]]) - min(dataset1[[2]])
> range_GPA
[1] 4
> sd(dataset1[[2]])
[1] 0.7407454
```
{% endtab %}
{% endtabs %}

**Ex 20**. Data Set 1을 이용하여 다음을 구하라.

a. 이 데이터 세트가 모든 고등학생들의  데이터로 생각하자. 모집단의 범위와 표준편차$$(\sigma)$$를 계산하라.

b. 이 모집지단에서 무작위 표본으로 제일 처음의 25개 데이터를 선택하였다. 이  표본의 범위와 표준편차$$(s)$$를 구하라. 이 값들을 \(a\)에서 구한 결과와 비교하라.

c.  이 모집단에서 무작위 표본으로 그 다음 25개 데이터를 선택하였다. 이  표본의 범위와 표준편차$$(s)$$를 구하라. 이 값들을 \(a\)에서 구한 결과와 비교하라.













