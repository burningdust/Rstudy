# R_study_Ch02


# Ch02. 데이터 분석을 위한 기본 다지기

## 02-2 데이터의 생김새

### 벡터

벡터 생성: 변수명 \<- c(값)

``` r
# 숫자형 벡터 생성
ex_vector1 <- c(-1, 0, 1)
ex_vector1
```

    [1] -1  0  1

mode() 데이터 유형 확인 함수, 정수와 실수를 숫자형으로 표시

str() 데이터 유형과 값 확인 함수

typeof() 데이터형만 출력, 정수와 실수 구분

length() 데이터 길이 확인 함수

``` r
# 숫자형 벡터 속성과 길이 확인하기
mode(ex_vector1)
```

    [1] "numeric"

``` r
str(ex_vector1)
```

     num [1:3] -1 0 1

``` r
length(ex_vector1)
```

    [1] 3

``` r
# 문자형 벡터 생성하기
ex_vector2 <- c("Hello", "Hi~!")
ex_vector2
```

    [1] "Hello" "Hi~!" 

``` r
ex_vector3 <- c("1", "2", "3")
ex_vector3
```

    [1] "1" "2" "3"

``` r
# 문자형 데이터 속성과 길이 확인하기
mode(ex_vector2)
```

    [1] "character"

``` r
str(ex_vector2)
```

     chr [1:2] "Hello" "Hi~!"

``` r
mode(ex_vector3)
```

    [1] "character"

``` r
str(ex_vector3)
```

     chr [1:3] "1" "2" "3"

``` r
# 논리형 벡터 생성하고 속성 확인하기
ex_vector4 <- c(TRUE, FALSE, TRUE, FALSE)
ex_vector4
```

    [1]  TRUE FALSE  TRUE FALSE

``` r
mode(ex_vector4)
```

    [1] "logical"

``` r
str(ex_vector4)
```

     logi [1:4] TRUE FALSE TRUE FALSE

데이터 삭제: remove() 또는 rm()

``` r
# 데이터  세트 삭제하기
remove(ex_vector2)
rm(ex_vector3)
```

범주형 자료: factor(범주화할 자료, labels = c(“범주”, …))

``` r
# 범주형 데이터 생성하기
ex_vector5 <- c(2, 1, 3, 2, 1)
ex_vector5
```

    [1] 2 1 3 2 1

``` r
cate_vector5 <- factor(ex_vector5, labels = c("Apple", "Banana", "Cherry"))
cate_vector5
```

    [1] Banana Apple  Cherry Banana Apple 
    Levels: Apple Banana Cherry

행렬: matrix(벡터, nrow=행, ncol=열)

``` r
# 행렬 데이터 생성하기
x <- c(1, 2, 3, 4, 5, 6)
matrix(x, nrow = 2, ncol = 3)
```

         [,1] [,2] [,3]
    [1,]    1    3    5
    [2,]    2    4    6

``` r
matrix(x, nrow = 3, ncol = 2)
```

         [,1] [,2]
    [1,]    1    4
    [2,]    2    5
    [3,]    3    6

``` r
# 옵션 추가로 결과 비교하기
x <- c(1, 2, 3, 4, 5, 6)
matrix(x, nrow = 2, ncol = 3)
```

         [,1] [,2] [,3]
    [1,]    1    3    5
    [2,]    2    4    6

``` r
matrix(x, nrow = 2, ncol = 3, byrow = T)
```

         [,1] [,2] [,3]
    [1,]    1    2    3
    [2,]    4    5    6

배열: array(변수명, dim = c(행, 열, 차원))

``` r
# 배열 생성하기
y <- c(1, 2, 3, 4, 5, 6)
array(y, dim = c(2, 2, 3))
```

    , , 1

         [,1] [,2]
    [1,]    1    3
    [2,]    2    4

    , , 2

         [,1] [,2]
    [1,]    5    1
    [2,]    6    2

    , , 3

         [,1] [,2]
    [1,]    3    5
    [2,]    4    6

리스트: list()

``` r
# 리스트 생성하기
list1 <- list(c(1, 2, 3), "Hello")
list1
```

    [[1]]
    [1] 1 2 3

    [[2]]
    [1] "Hello"

``` r
# 변수 속성 확인하기
str(list1)
```

    List of 2
     $ : num [1:3] 1 2 3
     $ : chr "Hello"

리스트에서는 대괄호를 2개 겹쳐서 인덱스 표현

``` r
# 리스트의 첫 번째 변수 호출
list1[[1]]
```

    [1] 1 2 3

데이터 프레임: data.frame(변수1, 변수2, …)

``` r
# 데이터 프레임 생성하기
ID <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
SEX <- c("F", "M", "F", "M", "M", "F", "F", "F", "M", "F")
AGE <- c(50, 40, 28, 50, 27, 23, 56, 47, 20, 38)
AREA <- c("서울", "경기", "제주", "서울", "서울", "서울", "경기", "서울", "인천", "경기")
dataframe_ex <- data.frame(ID, SEX, AGE, AREA)
dataframe_ex
```

       ID SEX AGE AREA
    1   1   F  50 서울
    2   2   M  40 경기
    3   3   F  28 제주
    4   4   M  50 서울
    5   5   M  27 서울
    6   6   F  23 서울
    7   7   F  56 경기
    8   8   F  47 서울
    9   9   M  20 인천
    10 10   F  38 경기

``` r
# 변수 속성 확인하기
str(dataframe_ex)
```

    'data.frame':   10 obs. of  4 variables:
     $ ID  : num  1 2 3 4 5 6 7 8 9 10
     $ SEX : chr  "F" "M" "F" "M" ...
     $ AGE : num  50 40 28 50 27 23 56 47 20 38
     $ AREA: chr  "서울" "경기" "제주" "서울" ...
