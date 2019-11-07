# 2-3. Exercises

## 1. Basic Exercises

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
x  1 2 7f  1 2 1
```

**Ex 6.** data frequency table로 표현된 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
x  -1 0 1 4f   1 1 2 1
```



## 2. Applications Exercies

**Ex 7.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
122 162 123 145 148 120 147 160 150 152
```

**Ex 8.** 다음 표본의 범위\(range\), 분산\(variance\) 그리고 표준편차\(standard deviation\)을 구하라.

```text
142 152 128 145 148 129 147 155 150 152
```



## 3. Additional Exercises

**Ex 9.** 다음의 표로 나타난 데이터 세트가 있다.

```text
x 26 27 28 29 30 31 32f  3  4 16 12  6  2  1
```

a. 이 표를 이용하여 $$\Sigma x$$ 와 $$\Sigma x^2$$ 을 구하라.

b. 위의 결과를 이용하여 표본 평균과 표본 표준편차를 구하라. 



**Ex 10.** 다음의 데이터에 대하여 표본 표준편차를 구하라.

```text
x    1    2    3    4    5    6    7    8    9   10f  284  208   98   56   28   12    8    2    3    1
```



**Ex 11.** 자동차 수리센터에서 수리비 청서를 49건 무작위로 선택하였다. 그 데이터를 stem and leaf diagram으로 정렬하였다. \(stem은 천단위, leaf는 백단위로 표시되어 있으며  가장 큰 금액은 3,800이었다.\)

```text
  0 | 4  0 | 5688  1 | 0012444  1 | 55566777889  2 | 000001224  2 | 566778899  3 | 001124  3 | 568
```

a. 평균, 중앙값 그리고 최빈값을 구하라.

b. 범위\(range\)를 구하라.

c. 표본 표준편차를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
x <- c(35, 36, 38, 30, 30, 31, 31, 32, 34, 25, 26, 26, 27, 27, 28, 28,        29, 29, 20, 20, 20, 20, 20, 21, 22, 22, 24, 15, 15, 15, 16, 16,       17, 17, 17, 18, 18, 19, 10, 10, 11, 12, 14, 14, 14, 5, 6, 8, 8,        4)stem(x)# a.mean(x)   # meanmedian(x) # mediany <- table(x)   # modenames(which.max(y))# b.range <- max(x) - min(x); range# c.sd(x)
```
{% endtab %}

{% tab title="a." %}
```text
> # a.> mean(x)   # mean[1] 20.6
```
{% endtab %}

{% tab title="b." %}
```text
> median(x) # median[1] 20
```
{% endtab %}

{% tab title="c." %}
```text
> y <- table(x)   # mode> names(which.max(y))[1] "20"
```
{% endtab %}
{% endtabs %}

**Ex 12.** 표준 편차가 0인 데이터 세트의 특징에 대하여 서술하라.

**Ex 13.** 25개의 측정치로 구성된 데이터 세트의 표준편차가 0이다. 이 측정치 중의 하나가 17의 값을 가지고 있다. 나머지 24개 측정치는 어떻게 구성이 되는가?

**Ex 14.** 범위의 값이 0이고, 표본 평균이 2이 는 표본의 크기가 3인 데이터 세트를 작성하라.

**Ex 15.** 표본 분산 값이 0이고, 표본 평균이 1이 되는 표본 크기 3의 데이터 세트를 작성하라.

**Ex 16.** \(-1, 0, 1\) 표본은 평균이 0, 표준편차가 1이다. 평균이 0이고 표준편차가 1보다 더 큰 값을 갖는 표본 크기 3인 데이터 세트를 작성하라.

**Ex 17.** \(-1, 0, 1\) 표본은 평균이 0, 표준편차가 1이다. 평균이 0이고 표준편차가 1보다 더 작은큰 값을 갖는 표본 크기 3인 데이터 세트를 작성하라.

**Ex 18.** 다음과 같은 데이터 세트가 있다. 이 데이터 세트를 **Data Set 1**이라고 하자.

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
ds1 <- c(5, -2, 6, 14, -3, 0, 1, 4, 3, 3, 5)# asd(ds1)# bds2 <- ds1 + 3; ds2sd(ds2)# cds3 <- ds2 - 6; ds3sd(ds3)
```
{% endtab %}

{% tab title="a" %}
```text
> # a> sd(ds1)[1] 4.60632
```
{% endtab %}

{% tab title="b" %}
```text
> # b> ds2 <- ds1 + 3; ds2 [1]  8  1  9 17  0  3  4  7  6  6  8> sd(ds2)[1] 4.60632
```
{% endtab %}

{% tab title="c" %}
```text
> # c> ds3 <- ds2 - 6; ds3 [1]  2 -5  3 11 -6 -3 -2  1  0  0  2> sd(ds3)[1] 4.60632
```
{% endtab %}

{% tab title="d" %}
\(a\), \(b\), \(c\) have the same standard deviation. 

=&gt; sd\(x\) = sd\(x + a\) = sd\(x - a\)
{% endtab %}
{% endtabs %}

## **4.** LARGE DATA SET EXERCISES

{% file src="../.gitbook/assets/data1 \(7\).xls" caption="Data Set 1" %}

**Ex 19.** 1,000 명의 학생들의 SAT와 GPS 성적을 수록하고 있는 **Data Set 1**이 의 사이트에 수록되어 있다.

{% embed url="http://www.flatworldknowledge.com/sites/all/files/data1.xls" caption="http://www.flatworldknowledge.com/sites/all/files/data1.xls " %}

a. SAT 성적의 범위와 표본 표준편차를 구하라.

b. GPS 성적의 범위와 표본 표준편차를 구하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
install.packages("readxl")library(readxl)dataset1 <- read_excel("data1.xls")str(dataset1)# Data Set 1sat <- dataset1[[1]]gpa <- dataset1[[2]]# list of Data Sethead(sat)head(gpa)# a.range_SAT <- max(sat) - min(sat)range_SATsd(sat)# b.range_GPA <- max(gpa) - min(gpa)range_GPAsd(gpa)
```
{% endtab %}

{% tab title="Data Set 1" %}
```text
> str(dataset1)                                                                                                                > str(dataset1)Classes ‘tbl_df’, ‘tbl’ and 'data.frame':   1000 obs. of  2 variables: $ SAT Score  : num  1300 1520 1580 1430 1610 1230 1520 1320 1240 1480 ... $ College GPA: num  3.66 2.92 2.66 2.27 2.35 2.02 2.94 1.76 2.35 3.16 ...>> # list of Data Set> head(sat)[1] 1300 1520 1580 1430 1610 1230> head(gpa)[1] 3.66 2.92 2.66 2.27 2.35 2.02
```
{% endtab %}

{% tab title="a" %}
```text
> # a.> range_SAT <- max(sat) - min(sat)> range_SAT[1] 1350> sd(sat)[1] 212.5455
```
{% endtab %}

{% tab title="b" %}
```text
> # b.> range_GPA <- max(gpa) - min(gpa)> range_GPA[1] 4> sd(gpa)[1] 0.7407454
```
{% endtab %}
{% endtabs %}

**Ex 20**. **Data Set 1**의 SAT성적을 이용하여 다음을 구하라.

a. 이 데이터 세트가 모든 고등학생들의  데이터로 생각하자. 모집단의 범위와 표준편차$$(\sigma)$$를 계산하라.

b. 이 모집지단에서 무작위 표본으로 제일 처음의 25개 데이터를 선택하였다. 이  표본의 범위와 표준편차$$(s)$$를 구하라. 이 값들을 \(a\)에서 구한 결과와 비교하라.

c.  이 모집단에서 무작위 표본으로 그 다음 25개 데이터를 선택하였다. 이  표본의 범위와 표준편차$$(s)$$를 구하라. 이 값들을 \(a\)에서 구한 결과와 비교하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
dataset1 <- read_excel("data1.xls")str(dataset1)# Population Data Setsat <- dataset1[[1]]; head(sat)# a.range_SAT <- max(sat) - min(sat) ; range_SATsd(sat)# Sample Data Set : First 25 Observations.sat <- dataset1[[1]][1:25]; sat# b.range_SAT <- max(sat) - min(sat) ; range_SATsd(sat)# Sample Data Set : First 25 Observations.sat <- dataset1[[1]][26:50]; sat# c.range_SAT <- max(sat) - min(sat) ; range_SATsd(sat)
```
{% endtab %}

{% tab title="a" %}
```text
> # Population Data Set> sat <- dataset1[[1]]; head(sat)[1] 1300 1520 1580 1430 1610 1230> > # a.> range_SAT <- max(sat) - min(sat) ; range_SAT[1] 1350> sd(sat)[1] 212.5455
```
{% endtab %}

{% tab title="b" %}
```text
> # Sample Data Set : First 25 Observations.> sat <- dataset1[[1]][1:25]; sat [1] 1300 1520 1580 1430 1610 1230 1520 1320 1240 1480 1780 1870 1140 1580 1520 1510 1490 1760 1430 1630 1960 1330[23] 1520 1430 1390> > # b.> range_SAT <- max(sat) - min(sat) ; range_SAT[1] 820> sd(sat)[1] 197.5373
```
{% endtab %}

{% tab title="c" %}
```text
> # Sample Data Set : Next 25 Observations.> sat <- dataset1[[1]][26:50]; sat [1] 1700 1320 1540 1510 1120 1690 1870 1450 1430 1850 1510 1510 1700 1330 1820 1360 1820 1670 1690 1330 1520 1180[23] 1700 1430 1330> > # c.> range_SAT <- max(sat) - min(sat) ; range_SAT[1] 750> sd(sat)[1] 209.6052
```
{% endtab %}
{% endtabs %}

**Ex 21**. **Data Set 1**의 GPA성적을 이용하여 다음을 구하라.

a. 이 데이터 세트가 모든 고등학생들의  데이터로 생각하자. 모집단의 범위와 표준편차$$(\sigma)$$를 계산하라.

b. 이 모집지단에서 무작위 표본으로 제일 처음의 25개 데이터를 선택하였다. 이  표본의 범위와 표준편차$$(s)$$를 구하라. 이 값들을 \(a\)에서 구한 결과와 비교하라.

c.  이 모집단에서 무작위 표본으로 그 다음 25개 데이터를 선택하였다. 이  표본의 범위와 표준편차$$(s)$$를 구하라. 이 값들을 \(a\)에서 구한 결과와 비교하라.

**\[Solution\]**

{% tabs %}
{% tab title="R Code" %}
```text
dataset1 <- read_excel("data1.xls")str(dataset1)# Population Data Setgpa <- dataset1[[2]]; head(gpa)# a.range_GPA <- max(gpa) - min(gpa) ; range_GPAsd(gpa)# Sample Data Set : First 25 Observations.gpa <- dataset1[[2]][1:25]; gpa# b.range_GPA <- max(gpa) - min(gpa) ; range_GPAsd(gpa)# Sample Data Set : Next 25 Observations.gpa <- dataset1[[2]][26:50]; gpa# c.range_GPA <- max(gpa) - min(gpa) ; range_GPAsd(gpa)
```
{% endtab %}

{% tab title="a" %}
```text
> # Population Data Set> gpa <- dataset1[[2]]; head(gpa)[1] 3.66 2.92 2.66 2.27 2.35 2.02> > # a.> range_GPA <- max(gpa) - min(gpa) ; range_GPA[1] 4> sd(gpa)[1] 0.7407454
```
{% endtab %}

{% tab title="b" %}
```text
> # Sample Data Set : First 25 Observations.> gpa <- dataset1[[2]][1:25]; gpa [1] 3.66 2.92 2.66 2.27 2.35 2.02 2.94 1.76 2.35 3.16 1.69 3.38 0.62 2.25 3.17 2.72 2.24 1.78 2.99 3.13 3.65 3.41[23] 0.73 1.87 2.04> > # b.> range_GPA <- max(gpa) - min(gpa) ; range_GPA[1] 3.04> sd(gpa)[1] 0.8080454
```
{% endtab %}

{% tab title="c" %}
```text
> # Sample Data Set : Next 25 Observations.> gpa <- dataset1[[2]][26:50]; gpa [1] 2.22 1.80 3.19 1.80 2.25 3.25 3.31 2.05 1.41 2.94 2.52 2.34 2.63 1.35 3.65 2.60 2.61 2.18 2.67 1.16 3.11 1.65[23] 2.05 3.00 2.28> > # c.> range_GPA <- max(gpa) - min(gpa) ; range_GPA[1] 2.49> sd(gpa)[1] 0.6578432> sd(gpa)[1] 0.6578432
```
{% endtab %}
{% endtabs %}

**Ex 22.** 다음의 데이터 세트는 특정 실험에 사용된 140마리 실험용 쥐의 생존 기간 데이터를 수록하고 있다. 

{% embed url="http://www.flatworldknowledge.com/sites/all/files/data7.xls" caption="http://www.flatworldknowledge.com/sites/all/files/data7.xls " %}

a. 성별에 상관없이 모든 쥐들의 생존기간의 범위와 표준편차를 구하라.

b. 수컷\(gender = "M"\) 쥐들의 범위와 표준편차를 구하라.

c. 암컷\(gender = "F"\) 쥐들의 범위와 표준편차를 구하라.

 **\[Solution A\]**

{% tabs %}
{% tab title="R Code" %}
```text
dataset <- read_excel("data7.xls")str(dataset)dataset$Gender <- as.factor(dataset$Gender)gender <- dataset[[2]]   ; head(gender)surv_day <- dataset[[3]] ; head(surv_day)# a.mean(surv_day)# b. c.aggregate(surv_day~gender, FUN=mean)
```
{% endtab %}

{% tab title="Data Set" %}
```text
> str(dataset)Classes ‘tbl_df’, ‘tbl’ and 'data.frame':   140 obs. of  3 variables: $ ID                  : num  1 2 3 4 5 6 7 8 9 10 ... $ Gender              : Factor w/ 2 levels "F","M": 1 2 1 2 1 2 2 1 2 1 ... $ Survival Time (days): num  554 680 484 706 396 737 664 362 719 512 ...> > dataset$Gender <- as.factor(dataset$Gender)> > gender <- dataset[[2]]   ; head(gender)[1] F M F M F MLevels: F M> surv_day <- dataset[[3]] ; head(surv_day)[1] 554 680 484 706 396 737
```
{% endtab %}

{% tab title="a" %}
```text
> # a.> mean(surv_day)[1] 553.4286
```
{% endtab %}

{% tab title="b. c." %}
```text
> # b. c.> aggregate(surv_day~gender, FUN=mean)  gender surv_day1      F 455.89332      M 665.9692
```
{% endtab %}
{% endtabs %}

**\[Solution B\]**

{% tabs %}
{% tab title="R Code" %}
```text
dataset <- read_excel("data7.xls")str(dataset)dataset$Gender <- as.factor(dataset$Gender)gender <- dataset[[2]]   ; head(gender)surv_day <- dataset[[3]] ; head(surv_day)# a.mean(surv_day)# or b. c. data <- data.frame(gender, surv_day); head(data)mean_surv_M <- mean(data$surv_day[data$gender == "M"]) ; mean_surv_Mmean_surv_F <- mean(data$surv_day[data$gender == "F"]) ; mean_surv_F
```
{% endtab %}

{% tab title="a" %}
```text
> str(dataset)Classes ‘tbl_df’, ‘tbl’ and 'data.frame':   140 obs. of  3 variables: $ ID                  : num  1 2 3 4 5 6 7 8 9 10 ... $ Gender              : Factor w/ 2 levels "F","M": 1 2 1 2 1 2 2 1 2 1 ... $ Survival Time (days): num  554 680 484 706 396 737 664 362 719 512 ...> > dataset$Gender <- as.factor(dataset$Gender)> > gender <- dataset[[2]]   ; head(gender)[1] F M F M F MLevels: F M> surv_day <- dataset[[3]] ; head(surv_day)[1] 554 680 484 706 396 737> # a.> mean(surv_day)[1] 553.4286
```
{% endtab %}

{% tab title="b. c." %}
```text
> # or b. c. > data <- data.frame(gender, surv_day); head(data)  gender surv_day1      F      5542      M      6803      F      4844      M      7065      F      3966      M      737> > mean_surv_M <- mean(data$surv_day[data$gender == "M"]) ; mean_surv_M[1] 665.9692> mean_surv_F <- mean(data$surv_day[data$gender == "F"]) ; mean_surv_F[1] 455.8933
```
{% endtab %}
{% endtabs %}



