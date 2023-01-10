## 1.	Написати функцію pmean, яка обчислює середнє значення (mean) забруднення сульфатами або нітратами серед заданого переліка моніторів. Ця функція приймає три аргументи: «directory», «pollutant», «id». Directory – папка, в якій розміщені дані, pollutant – вид забруднення, id – перелік моніторів. Аргумент id має значення за замовчуванням 1:332. Функція повинна ігнорувати NA значення. ## 
setwd("C:/Users/Acer/OneDrive - НАСОА/Робочий стіл/specdata") <br>
getcsv = function(directory, file_id) { <br>
  return(read.csv(paste0(directory, "/", formatC(file_id, width = 3, flag = "0"), ".csv"))) <br>
} <br> 
<h4>Функція:</h4> 
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

