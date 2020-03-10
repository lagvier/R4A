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

library(reshape2)
wide = reshape(long, direction = 'wide',idvar = 'ï..Year', 
timevar = 'variable')
names(wide) <- gsub('value.', '', names(wide))
names(wide) <- gsub('.milk', '', names(wide))

install.packages(c('reshape', 'reshape2'), dependencies = T)

subset(milk, `ï..Year`<1998, select = c('Camel.milk'))
merge(data1, data2, by = ýear, all = T)
rbind(milk, milk)
cbind(milk, country = 'kenya')


for(i in unique(milk$ï..Year)){
  cat(i, '\n')
}

apply(milk, 1, length) #count columns per row
apply(milk, 2, length)  # count rows per column


milk$a<-NULL
milk$b<-NULL

# milk$Camel.milk <- gsub(',', '',
#                        as.character(milk$Camel.milk))


# save/write
# change to the correct directory in your computer
write.csv(milk, 'C:/Users/data/modi milk production.csv',
          row.names = FALSE) 

```
