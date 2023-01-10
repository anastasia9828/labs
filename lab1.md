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
A
> 0.5     1.3    3.5 <br>
> 3.9     131.0  2.8 <br>
> 0.0     2.2    4.6 <br>
> 2.0     7.0    5.1 <br>
Markdown | не такой | красивый
--- | --- | ---
*Но выводится* | `так же` | **клево**
1 | 2 | 3
