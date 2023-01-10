## 1.	Написати функцію pmean, яка обчислює середнє значення (mean) забруднення сульфатами або нітратами серед заданого переліка моніторів. Ця функція приймає три аргументи: «directory», «pollutant», «id». Directory – папка, в якій розміщені дані, pollutant – вид забруднення, id – перелік моніторів. Аргумент id має значення за замовчуванням 1:332. Функція повинна ігнорувати NA значення. ## 
setwd("C:/Users/Acer/OneDrive - НАСОА/Робочий стіл/specdata") <br>
getcsv = function(directory, file_id) { <br>
  return(read.csv(paste0(directory, "/", formatC(file_id, width = 3, flag = "0"), ".csv"))) <br>
} <br> 
<h4>Функція pmean:</h4> 
pmean = function(directory, pollutant, id = 1:332) { <br>
  all = NULL <br>
  for (i in id) { <br>
    all = c(all, getcsv(directory, i)[[pollutant]]) <br>
  } <br>
  return(mean(all, na.rm = TRUE)) <br>
} <br>
pmean("specdata", "sulfate", 1:3) <br>

> [1] 4.389262

pmean("specdata", "sulfate", 1:10)
> [1] 4.064128

pmean("specdata", "sulfate", 55)
> [1] 3.587319

pmean("specdata", "nitrate")
> [1] 1.702932

## 2.	Написати функцію complete, яка виводить кількість повних спостережень(the number of completely observed cases) для кожного файлу. Функція приймає два аргументи: «Directory» та «id» та повертає data frame, в якому перший стовпчик – ім’я файлу, а другий – кількість повнихспостережень. ##
<h4>Функція complete:</h4>
complete = function(directory, id = 1:332) { <br> 
  nobs = NULL <br>
  for (i in id) { <br>
    nobs = c(nobs, nrow(na.omit(getcsv(directory, i)))) <br>
  } <br>
  return(data.frame(id, nobs)) <br>
} <br>

complete("specdata", 1)
>   id nobs <br>
> 1  1  117 <br>

complete("specdata", c(2, 4, 8, 10, 12))
>   id nobs <br>
> 1  2 1041 <br>
> 2  4  474 <br>
> 3  8  192 <br>
> 4 10  148 <br>
> 5 12   96 <br>

complete("specdata", 50:60)
 >  id nobs <br>
> 1  50  459 <br>
> 2  51  193 <br>
> 3  52  812 <br>
> 4  53  342 <br>
> 5  54  219 <br>
> 6  55  372 <br>
> 7  56  642 <br>
> 8  57  452 <br>
> 9  58  391 <br>
> 10 59  445 <br>
> 11 60  448 <br>

## 3.	Написати функцію corr, яка приймає два аргументи: directory (папка, де знаходяться файли спостережень) та threshold (порогове значення, за замовчуванням дорівнює 0) та обчислює кореляцію між сульфатами та нітратами для моніторів, кількість повних спостережень для яких більше порогового значення. Функція повинна повернути вектор значень кореляцій. Якщо ні один монітор не перевищує порогового значення, функція повинна повернути numeric вектор довжиною 0. Для обчислення кореляції між сульфатами та нітратами використовуйте вбудовану функцію ##
<h4>Функція corr:</h4>
corr = function(directory, threshold = 0) { <br> 
  corelations = numeric() <br>
  for (i in 1:332) { <br>
    full_obs = na.omit(getcsv(directory, i)) <br>
    if (nrow(full_obs) > threshold) { <br>
      corelations = c(corelations, cor(full_obs$sulfate, full_obs$nitrate)) <br>
    } <br>
  } <br>
  return(corelations) <br>
} <br>
