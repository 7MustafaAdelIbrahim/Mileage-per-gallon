## Content

### Sources and Relevant Information:
The [dataset](https://archive.ics.uci.edu/ml/datasets/auto+mpg) is downloaded from UCI Machine Learning Repository which contains one row per car model.
This dataset was taken from the StatLib library which is
maintained at ***Carnegie Mellon University**** and was 
used in the July 7, 1993 American Statistical Association Exposition.
This dataset is a slightly modified version of the dataset provided in
the StatLib library. In line with the use by Ross Quinlan (1993) in
predicting the attribute "mpg", 8 of the original instances were removed 
because they had unknown values for the "mpg" attribute. The original 
dataset is available in the file "auto-mpg.data-original".
"The data concerns city-cycle fuel consumption in miles per gallon,
to be predicted in terms of 3 multivalued discrete and 5 continuous
attributes." (Quinlan, 1993)

#### ***Number of Instances: 398. Number of Attributes: 9***
#### The Data Dictionary 


| Column        | Contains      |       
| ------------- | ------------- | 
| MPG  | Miles per Gallon.| 
| cylinders  | No. of Cylinders.| 
| displacement  | Engine size.| 
|horsepower |	Engine power.|
|Weight| Car weight.|
|acceleration| how fast can accelerate in seconds|
|model_year| Car year model.|
|Origin | Car country of manufacture.|
|car_name | Car model.|

The model that you'll be building will depend on the physical characteristics of the cars rather than the model names or manufacturers, so you'll remove the corresponding columns from the data. [model_year, car_name]

### conclusions

- 63%of cars  are American, about 17.5% are European, and about 19.5% are Japanese.
![origin](https://user-images.githubusercontent.com/84151016/159078699-e515960d-1ad3-4ab3-83b0-a003d532f6af.png)

But they may be important in the analysis. We'll take about year in this readme file. 
Butfor the name, Somewhat expected observation is that the models differ greatly according to the country in which they are manufactured. As every country has it's own company and it's brands in the field of car.
For example, we foundt that:

![24322577-ebe6a4c02f5e7948cf0424ff724d13f5](https://user-images.githubusercontent.com/84151016/159092200-5838876f-b8ff-4768-b91d-8fe16cd6d22b.png)


The relation between origin country and car model.

![car and model](https://user-images.githubusercontent.com/84151016/159081199-0c7a5386-0e66-4a10-bb78-a4372f38d39b.png)


There are little number cars in our dataset whose high-efficiency, and which can travel a large number of miles per gallon.

![performance](https://user-images.githubusercontent.com/84151016/159078720-ffa87a65-9638-4357-9205-b60004170362.png)


Cars with american origin country are the least efficient, as the average is 18 MPG, and reach 39 mpg as the maximum.‎
But the Japanese ones, they reach 46 mpg, and the European reaches 44 mpg.

![performance and mpg](https://user-images.githubusercontent.com/84151016/159079264-996f1162-4379-40ee-824b-4c346a1023de.png)


This is due to several reasons, but before we talk about the reasons, it's worth to mentioned that the average MPG has increased over time, but with a high standard deviation. Meaning that there is high differences or variation in MPG.
This is because the MPG for American cars increased in 1971 from 1970, and decreased in the period from 1971 to 1973 to the point where it decreased from 1970. It increased in the period from 1973 to 1974 and it happened A minor setback in 1975. Then, it continues to increase almost regularly, but it is always less than the Japanese and European. But for the European and Japanese cars, the MPG was randomly increased and decreased and was always higher than the American one, and this is the reason ‎why the std is high.

![mpg over time](https://user-images.githubusercontent.com/84151016/159079912-bec6d2fa-a4c0-4ef5-ab49-7a99ea0f9da5.png)


#### Back to the reasons that American Arabs are the least efficient.

The 'horsepower' of a car is in an inverse or negative relationship with MPG, as the higher the horsepower, the less MPG; Because the car will burn more fuel. 
With each increase in horsepower, the MPG will be cut by -0.156. And American cars have large average horsepower compared to Japanese and European ones
The number of cylinders, the higher the number of cylinders in a car, the more petrol it burns. As the number of cylinders increases by 1, the mpg decreases by 3.57.

![displacment + mpg](https://user-images.githubusercontent.com/84151016/159080233-4bfe2b36-61d8-477d-8ae8-10f23a197caf.png)


The number of cylinders in American vehicles is greater than Japanese and European ones. 
Whereas, the number of cylinders in American cars starts from 4 and reaches 8, while the Japanese and European cars are almost 4 only.

![cylinders+ horsepower](https://user-images.githubusercontent.com/84151016/159080119-d1c18c83-24a1-4a56-96c7-b4a54a741b63.png)
![no cylinders](https://user-images.githubusercontent.com/84151016/159080121-f612e83c-d21d-4aae-b204-41c495ba3bf8.png)

![cylinders + origin](https://user-images.githubusercontent.com/84151016/159080297-fd5a92b7-d82d-4cd4-9397-94805e5727cb.png)

Weight of vehicles is in an inverse negative relationship with MPG, and this is normal because resistance will increase, fuel consumption will increase, and therefore MPG will decrease. American vehicles are the most in weight.
As for Japanese and European Arabic, the MPG changes randomly, increases and decreases with time. And this is the explanation, because it has a great stander-deviation.

![weight + mpg](https://user-images.githubusercontent.com/84151016/159080136-3f1894be-3f80-4bb4-be75-53d74fccaf63.png)


Displacement or engine capacity - the higher the MPG, the lower the MPG
And American Arabs were the highest in displacement, ranging from 80 to 460, while the Japanese were from 60 to 170, and the European ones were similar.

![displacment + mpg](https://user-images.githubusercontent.com/84151016/159080143-015d8ab6-d9b3-4d2a-9cbb-9c621c63a843.png)

The amount of acceleration is not very effective and it’s along is not a good indicator for mpg. 
And the distribution has a bell shaped, and a small number of cars in the dataset which can reach a speed of 60 miles per hours in a few seconds, and they were European.![acc + mpg](https://user-images.githubusercontent.com/84151016/159080468-f4f939bc-6144-45cc-98f6-5b1b93f4d51e.png)


![acc](https://user-images.githubusercontent.com/84151016/159080465-a6a9e651-d26a-44be-b184-3c9be15d0528.png)


Our target is a building predictive model based on the physical characteristics of each Arabic, meaning the year, name columns are not important, and we do the machine learning model.

![car models](https://user-images.githubusercontent.com/84151016/159078753-2a8cd264-9f8c-47cc-8873-a7bc0d75374c.png)


[opel, saab, mercedes-benz, bmw…etc] is with Europe orign country.
[Toyota, Datsun, honda…etc] is with japanes origin country. 
[Ford, Chevrolet, Plymouth, amc, dodge…etc] are American.

wich makesn sense, and somewhat expected.


## Inspiration
I have used this dataset for practicing my exploratory analysis skills and bulding a machine learning model to predict mileage per gallon.
