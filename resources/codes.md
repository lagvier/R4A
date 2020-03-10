```


# read data
# change to the correct directory in your computer
milk <- read.csv('C:/Users/data/milk production.csv',
         header = T) 

# overview of data
head(milk, n=3) # top n records
milk[c(1:3),c(3,5)] # slicing

head(milk[,2:4], n=3) # top n records
head(milk[c(1:3),c(3,5)], n=1) # top n records

# structure and class
str(milk)

# transformation
milk$a <- as.numeric(milk$Cow.milk) # convert to numeric

milk$b <- as.character(milk$Cow.milk) # convert to numeric
milk$b <- gsub(',', '', milk$b) # string conversion 
milk$Cow.milk <- as.numeric(milk$b)

library(dplyr)
milk <- mutate(milk, Cow.milk = as.character(Cow.milk),
               Camel.milk = as.character(Camel.milk),
               Sheep.milk = as.character(Sheep.milk),
               Goat.milk = as.character(Goat.milk),
               Total.production = as.character(Total.production)
               )

milk <- mutate(milk, Cow.milk = gsub(',', '', Cow.milk),
               Camel.milk = gsub(',', '', Camel.milk),
               Sheep.milk = gsub(',', '', Sheep.milk),
               Goat.milk = gsub(',', '', Goat.milk),
               Total.production = gsub(',', '', Total.production)
)
milk <- mutate(milk, Cow.milk = as.numeric(Cow.milk),
               Camel.milk = as.numeric(Camel.milk),
               Sheep.milk = as.numeric(Sheep.milk),
               Goat.milk = as.numeric(Goat.milk),
               Total.production = as.numeric(Total.production)
)

# install.packages(c('reshape', 'reshape2'), dependencies = T)
library(reshape2)
# milk <- read.csv('C:/Users/data/milk production.csv',
#         header = T) 
long = melt(milk, id = "ï..Year")
long <- mutate(long, value = as.character(value))
long <- mutate(long, value = gsub(',', '', value))
long <- mutate(long, value = as.numeric(value))

# rename variables
library(plyr)
long = rename(long, c("ï..Year"="Year", "value"="Score"))
long <- mutate(long, variable = gsub(".milk", "", 
                                     as.character(variable)))
# long$valuable<-NULL # delete the variable column
library(reshape)
# assignment operator: = , <-
wide = reshape(long, direction = 'wide',idvar = 'Year', 
               timevar = 'variable')
names(wide) <- gsub('Score.', '', names(wide))

# logical operators: !=, ==, >, <, >=,<=, %in%
subset(wide, Year==2010, select = c('Camel', ""))

letters[1:7] %in% c("c", "f")
# grepl() and grep()
a <- c('kenya', 'uganda', 'tanzania', 'usa', 'italy', 'iran')
grepl('^u', a)
grepl('a$', a)

grep('^u', a)
grep('a$', a)

grep('^u', a, value = TRUE)
grep('a$', a, value = TRUE)

data = as.data.frame(cbind(
  Year = c(min(wide$Year):max(wide$Year)),
  Age = ifelse(Year<2000, "Old", "New")
))
# merge data
alldata = merge(wide, data, data2, by = "Year")

# append data
rbind(milk, milk) 

# add new column to the data with the value indicate
cbind(milk, country = 'kenya') 


for(i in unique(alldata$Age)){
  cat(i, '\n')
}

apply(wide[,-1], 1, mean) #mean columns per row
apply(wide[,-1], 2, mean)  # mean rows per column

# save/write
# change to the correct directory in your computer
write.csv(milk, 'C:/Users/data/modi milk production.csv',
          row.names = FALSE) 

```
