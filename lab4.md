## 1. Які назви стовпців файлу даних? ##
csv = read.csv("C:/users/Анастасия Бойко/Рабочий стол/hw1_data.csv") <br>
colnames(csv)
> [1] "Ozone"   "Solar.R" "Wind"    "Temp"    "Month"   "Day" 
## 2.Виведіть перші 6 строк фрейму даних. ##
head(csv, 6)
>  Ozone Solar.R Wind Temp Month Day <br>
> 1    41     190  7.4   67     5   1 <br>
> 2    36     118  8.0   72     5   2 <br>
> 3    12     149 12.6   74     5   3 <br>
> 4    18     313 11.5   62     5   4 <br>
> 5    NA      NA 14.3   56     5   5 <br>
> 6    28      NA 14.9   66     5   6 <br>

## 3. Скільки спостерігань (строк) в дата фреймі? ##
nrow(csv)
> [1] 153
