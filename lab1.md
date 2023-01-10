## 1.	Створити змінні базових (atomic) типів. Базові типи: character, numeric, integer, complex, logical. ##
character <- "Приклад" <br>
numeric <- 8 <br>
integer <- 8L <br>
complex <- 8 + 5i <br>
logical <- TRUE <br>
> character <- "Приклад" <br>
> numeric <- 8 <br>
> integer <- 8L <br>
> complex <- 8 + 5i <br>
> logical <- TRUE <br>
## 2.	Створити вектори, які: містить послідовність з 5 до 75; містить числа 3.14, 2.71, 0, 13; 100 значень TRUE. ## 
numeric_vector <- 5:75 <br>
vector_with_math <- c(pi, 2.71, 0, 13) <br>
logical_vector <- rep(TRUE, 100) <br>
> numeric_vector <- 5:75 <br>
> vector_with_math <- c(pi, 2.71, 0, 13) <br>
> logical_vector <- rep(TRUE, 100) <br>
## 3.Створити наступну матрицю за допомогою matrix, та за допомогою cbind або rbind ##
A <- matrix(c(0.5, 3.9, 0, 2, 1.3, 131, 2.2, 7, 3.5, 2.8, 4.6, 5.1), nrow = 4, ncol = 3) <br>
A <br>
> <table>
>    1        2      3 <br>
> 1) 0.5     1.3    3.5 <br>
> 2) 3.9     131.0  2.8 <br>
> 3) 0.0     2.2    4.6 <br>
> 4) 2.0     7.0    5.1 <br> </table>
a <- c(0.5, 3.9, 0, 2) <br>
b <- c(1.3, 131, 2.2, 7) <br>
c <- c(3.5, 2.8, 4.6, 5.1) <br>
cbind_matrix <- cbind(a, b, c) <br>
cbind_matrix <br> 

> <table>
>    a        b      c <br>
> 1) 0.5     1.3    3.5 <br>
> 2) 3.9     131.0  2.8 <br>
> 3) 0.0     2.2    4.6 <br>
> 4) 2.0     7.0    5.1 <br> </table>

a <- c(0.5, 1.3, 3.5) <br>
b <- c(3.9, 131, 2.8) <br>
c <- c(0, 2.2, 4.6) <br>
d <- c(2, 7, 5.1) <br>
rbind_matrix = rbind(a, b, c, d) <br>
rbind_matrix <br>
> <table>
>    1        2      3 <br>
> a) 0.5     1.3    3.5 <br>
> b) 3.9     131.0  2.8 <br>
> c) 0.0     2.2    4.6 <br>
> d) 2.0     7.0    5.1 <br> </table>

## 4.Створити довільний список (list), в який включити всі базові типи. ##
basic_list <- list(9, 9L, TRUE, 3 + 8i, "Hello world") <br>
basic_list <br>
> basic_list <br>
> [[1]] <br>
> [1] 9 <br>
> [[2]] <br>
> [1] 9 <br>
> [[3]] <br>
> [1] TRUE <br>
> [[4]] <br>
> [1] 3+8i <br>
> [[5]] <br>
> [1] "Hello world" <br>
## 5.	Створити фактор з трьома рівнями «baby», «child», «adult». ## 
x <- factor(c("baby", "child", "child", "adult", "adult", "adult", "child", "baby", "baby"), levels = c("baby", "child", "adult")) <br>
x <br>
> [1] baby  child child adult adult adult child baby  baby <br>
> Levels: baby child adult <br>
## 6.	Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. Знайти кількість значень NA. ##
vector_NA <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11) <br>
index_NA <- min(which(is.na(vector_NA))) <br>
index_NA <br>
> index_NA <br>
> [1] 5 <br>
length_NA <- length(which(is.na(vector_NA))) <br>
length_NA <br>
> length_NA <br>
> [1] 3 <br>
## 7.	Створити довільний data frame та вивести в консоль.## <br>  
a <- c(11, 13, 14) <br>
b <- c("aa", "ab", "ac") <br>
c <- c(FALSE, FALSE, TRUE) <br>
data_frame <- data.frame(num = a, char = b, bool = c) <br>
data_frame <br>
> data_frame <br>
 > num char  bool <br>
> 1  11   aa FALSE <br>
> 2  13   ab FALSE <br>
> 3  14   ac  TRUE <br>

