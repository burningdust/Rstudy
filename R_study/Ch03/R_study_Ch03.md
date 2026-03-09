# R_study_Ch03


# Ch03. R 프로그래밍 익히기

## 03-1 변수와 함수

``` r
# 숫자와 문자 변수 생성하기
x <- 10
x
```

    [1] 10

``` r
y <- "HI"
y
```

    [1] "HI"

``` r
x <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
max(x)
```

    [1] 10

``` r
sum(x)
```

    [1] 55

``` r
min(x)
```

    [1] 1

``` r
sum_x <- sum(x)
```

``` r
# Hello World 문자 출력하기
print("Hello World")
```

    [1] "Hello World"

``` r
# 1부터 100까지 더한 값을 출력하기
a <- sum(1:100)
a
```

    [1] 5050

``` r
# 오늘 날짜 출력하기
Sys.Date()
```

    [1] "2026-03-09"

함수 만들기

함수명 \<- function(매개변수){

…

return(결괏값)

}

``` r
# 숫자 3개 곱하기
multi_three_return <- function(x, y, z){
  res <- x*y*z
  return(res)
}
multi_three_return(3, 5, 6)
```

    [1] 90

return() 값 반환

cat() 출력

``` r
# return()을 사용하여 사용자 정의 함수 생성
multi_three_return <- function(x, y, z){
  res <- x*y*z
  return(res)
}

# 함수 호출
multi_three_return(3, 5, 6)
```

    [1] 90

``` r
# 변수에 저장한 후 출력
a <- multi_three_return(3, 5, 6)
a
```

    [1] 90

``` r
# cat()을 사용하여 사용자 정의 함수 생성
multi_three_cat <- function(x, y, z){
  res <- x*y*z
  cat(res)
}

# 함수 호출
multi_three_cat(3, 5, 6)
```

    90

``` r
# 변수에 저장한 후 출력
b <- multi_three_cat(3, 5, 6)
```

    90

``` r
b
```

    NULL

cat() 여러 변수 출력 가능

print() 입력된 첫번째 숫자 또는 문자만 출력, 변수 하나만 가능

``` r
# 여러 숫자 출력
print(1, 2, 3)
```

    [1] 1

``` r
cat(1, 2, 3)
```

    1 2 3

``` r
#숫자, 문자열 출력
print(1, 2, 3, "hello")
```

    [1] 1

``` r
cat(1, 2, 3, "hello")
```

    1 2 3 hello

``` r
# 여러 개 변수 출력
x <- 4:6
y <- "hello world"
print(x, y)
```

    Warning in print.default(x, y): NAs introduced by coercion

    Error in print.default(x, y): invalid printing digits -2147483648

``` r
cat(x, y)
```

    4 5 6 hello world

## 03-2 패키지

패키지 설치: install.packages()

``` r
# reshape2 패키지 설치하기
install.packages("reshape2")
```

설치한 패키지 확인: library()

``` r
# 설치한 패키지 확인하기
library()
```

패키지 로드: library(패키지), 따옴표 사용X

``` r
# 설치한 패키지 로드하기
library(reshape2)
```

    Warning: package 'reshape2' was built under R version 4.3.3

패키지 삭제: remove.packages(“패키지”)

``` r
remove.packages("reshape2")
```

## 03-3 조건문과 반복문

``` r
# 변수에 값을 할당하기
A <- 2
A
```

    [1] 2

``` r
B = 10
B
```

    [1] 10

\<-가 =보다 우선순위가 높음

``` r
C = D <- 5
C
```

    [1] 5

``` r
D
```

    [1] 5

``` r
G <- E = 10
```

    Error: object 'G' not found

함수 인자에 값을 넣을 때 =는 사용 불가

``` r
sum(x <- 1)
```

    [1] 1

``` r
x
```

    [1] 1

``` r
sum(y = 1)
```

    [1] 1

``` r
y
```

    [1] "hello world"

%/%: 몫

%%: 나머지

\*\* 또는 ^: 제곱

``` r
# 산술 연산자
1 + 2
```

    [1] 3

``` r
5 - 3
```

    [1] 2

``` r
3 * 7
```

    [1] 21

``` r
20 / 4
```

    [1] 5

``` r
-1 + 3
```

    [1] 2

``` r
20 %/% 7
```

    [1] 2

``` r
20 %% 7
```

    [1] 6

``` r
6^2
```

    [1] 36

``` r
6 ** 2
```

    [1] 36

``` r
# 관계 연산자
5 > 3
```

    [1] TRUE

``` r
3 >= 6
```

    [1] FALSE

``` r
5 < 3
```

    [1] FALSE

``` r
5 <= 6
```

    [1] TRUE

``` r
5 == 5
```

    [1] TRUE

``` r
5 != 5
```

    [1] FALSE

``` r
!5
```

    [1] FALSE

``` r
# 논리 연산자로 진릿값 확인하기
x <- 1:3
y <- 3:1
(x>0) & (y<1)
```

    [1] FALSE FALSE FALSE

``` r
(x>0) | (y>1)
```

    [1] TRUE TRUE TRUE

``` r
# 조건문으로 짝수 홀수 구분하기
a <- 10
if(a %% 2 == 0) {
  print("짝수입니다")
} else {
  print("홀수입니다")
}
```

    [1] "짝수입니다"

``` r
# 조건문으로 학점 분류하기
b <- 80
if(b >= 90) {
  print("A 학점입니다")
} else if (b >= 80) {
  print("B 학점입니다")
} else {
  print("C 학점입니다")
}
```

    [1] "B 학점입니다"

``` r
# for() 함수로 구구단 2단 출력하기
for(i in 1:9) {
  a <- 2*i
  print(a)
}
```

    [1] 2
    [1] 4
    [1] 6
    [1] 8
    [1] 10
    [1] 12
    [1] 14
    [1] 16
    [1] 18

``` r
# for() 함수로 구구단 2단부터 9단까지 출력하기
for(i in 2:9) {
  for(j in 1:9) {
    print(paste(i, "*", j, "=", i*j))
  }
}
```

    [1] "2 * 1 = 2"
    [1] "2 * 2 = 4"
    [1] "2 * 3 = 6"
    [1] "2 * 4 = 8"
    [1] "2 * 5 = 10"
    [1] "2 * 6 = 12"
    [1] "2 * 7 = 14"
    [1] "2 * 8 = 16"
    [1] "2 * 9 = 18"
    [1] "3 * 1 = 3"
    [1] "3 * 2 = 6"
    [1] "3 * 3 = 9"
    [1] "3 * 4 = 12"
    [1] "3 * 5 = 15"
    [1] "3 * 6 = 18"
    [1] "3 * 7 = 21"
    [1] "3 * 8 = 24"
    [1] "3 * 9 = 27"
    [1] "4 * 1 = 4"
    [1] "4 * 2 = 8"
    [1] "4 * 3 = 12"
    [1] "4 * 4 = 16"
    [1] "4 * 5 = 20"
    [1] "4 * 6 = 24"
    [1] "4 * 7 = 28"
    [1] "4 * 8 = 32"
    [1] "4 * 9 = 36"
    [1] "5 * 1 = 5"
    [1] "5 * 2 = 10"
    [1] "5 * 3 = 15"
    [1] "5 * 4 = 20"
    [1] "5 * 5 = 25"
    [1] "5 * 6 = 30"
    [1] "5 * 7 = 35"
    [1] "5 * 8 = 40"
    [1] "5 * 9 = 45"
    [1] "6 * 1 = 6"
    [1] "6 * 2 = 12"
    [1] "6 * 3 = 18"
    [1] "6 * 4 = 24"
    [1] "6 * 5 = 30"
    [1] "6 * 6 = 36"
    [1] "6 * 7 = 42"
    [1] "6 * 8 = 48"
    [1] "6 * 9 = 54"
    [1] "7 * 1 = 7"
    [1] "7 * 2 = 14"
    [1] "7 * 3 = 21"
    [1] "7 * 4 = 28"
    [1] "7 * 5 = 35"
    [1] "7 * 6 = 42"
    [1] "7 * 7 = 49"
    [1] "7 * 8 = 56"
    [1] "7 * 9 = 63"
    [1] "8 * 1 = 8"
    [1] "8 * 2 = 16"
    [1] "8 * 3 = 24"
    [1] "8 * 4 = 32"
    [1] "8 * 5 = 40"
    [1] "8 * 6 = 48"
    [1] "8 * 7 = 56"
    [1] "8 * 8 = 64"
    [1] "8 * 9 = 72"
    [1] "9 * 1 = 9"
    [1] "9 * 2 = 18"
    [1] "9 * 3 = 27"
    [1] "9 * 4 = 36"
    [1] "9 * 5 = 45"
    [1] "9 * 6 = 54"
    [1] "9 * 7 = 63"
    [1] "9 * 8 = 72"
    [1] "9 * 9 = 81"

paste() 나열된 값을 이어서 출력

행렬 연산: apply(x, margin, 함수)

-margin이 1이면 행, 2이면 열 적용

lapply(x, 함수): 연산 결과 리스트로 반환, 모든 자료형 사용 가능

sapply(x, 함수): 연산 결과 벡터로 반환, 모든 자료형 사용 가능

``` r
# apply()함수로 행렬 값 계산하기
x <- matrix(1:4, 2, 2)
x
```

         [,1] [,2]
    [1,]    1    3
    [2,]    2    4

``` r
apply(x, 1, sum)
```

    [1] 4 6

``` r
apply(x, 2, min)
```

    [1] 1 3

``` r
apply(x, 1, max)
```

    [1] 3 4

``` r
# iros 데이터 세트 구조 확인하기
str(iris)
```

    'data.frame':   150 obs. of  5 variables:
     $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
     $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
     $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
     $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
     $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...

``` r
View(iris)
```

``` r
# apply 함수로 iris 데이터 세트 값 처리하기
apply(iris[, 1:4], 2, sum)
```

    Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
           876.5        458.6        563.7        179.9 

``` r
apply(iris[, 1:4], 2, mean)
```

    Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
        5.843333     3.057333     3.758000     1.199333 

``` r
apply(iris[, 1:4], 2, min)
```

    Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
             4.3          2.0          1.0          0.1 

``` r
apply(iris[, 1:4], 2, max)
```

    Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
             7.9          4.4          6.9          2.5 

``` r
apply(iris[, 1:4], 2, median)
```

    Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
            5.80         3.00         4.35         1.30 

``` r
lapply(iris[, 1:4], sum)
```

    $Sepal.Length
    [1] 876.5

    $Sepal.Width
    [1] 458.6

    $Petal.Length
    [1] 563.7

    $Petal.Width
    [1] 179.9

``` r
sapply(iris[, 1:4], mean)
```

    Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
        5.843333     3.057333     3.758000     1.199333 
