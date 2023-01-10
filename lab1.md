library(caret)

# define the filename
filename <- "~/data/iris.csv"
# load the CSV file from the local directory
dataset <- read.csv(filename, header=FALSE)
# set the column names in the dataset
colnames(dataset) <- c("Sepal.Length","Sepal.Width","Petal.Length","Petal.Width","Species")

# create a list of 80% of the rows in the original dataset we can use for training
validationIndex <- createDataPartition(dataset$Species, p=0.80, list=FALSE)
# select 20% of the data for validation
validation <- dataset[-validationIndex,]
# use the remaining 80% of data to training and testing the models
dataset <- dataset[validationIndex,]

### SUMMARIZE DATASET ###

# 1. Dimensions of the dataset.
# 2. Types of the attributes.
# 3. Peek at the data itself.
# 4. Levels of the class attribute.
# 5. Breakdown of the instances in each class.
# 6. Statistical summary of all attributes.

# dimensions of dataset
dim(dataset)

# list types for each attribute
sapply(dataset, class)

# take a peek at the first 5 rows of the data
head(dataset)

# list the levels for the class
dataset$Species <- factor(dataset$Species)

# levels(dataset$Species) <- c('setosa','versicolor','virginica')

table(dataset$Species)

# summarize the class distribution
percentage <- prop.table(table(dataset$Species)) * 100

cbind(freq=table(dataset$Species), percentage=percentage)
