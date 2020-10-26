# Hotel-Operation-Analysis

This document describes the code in the Hotel Operation Analysis.

<h1>Data Preprocessing</h1>
<p>In the data preprocessing step, I focused on two parts. First is handling the outleirs and missing values in the dataset, and the second part is converting 
imbalanced data set into balanced one. </p>

<h3>Outliers and Missing values</h3>

<li>Outliers</li>
<p>To find out outliers, I used plots  to visualize the data points that differs significantly from other observations. However, though some points seems to 
be outliers, they are still in reasonable ranges. Therefore, I not only plot those data points, but also used standard deviation to define the outliers 
more accurately. </p>

<li>Missing values</li>
<p>Before handling missing values, I made a resesarch to understand the business models and metrics of the hotel operation to figure out the meanings of every data.
For example, the column "lead_time" means the time between booking date and arrive date, which is also an important factor to cancellation rate.</p>
<n></n>
<p>After understanding the dataset, I began working on missing values. First of all, I checked the the total of missing values in every column. If the missing
rate is over 30%, then I would drop it. In the dataset, the rate of column "company" is up to 94%, so I drop it. For other missing values, such as "children",
I used 0 to replace the missing value as I assumed that means no children. For the column "agent", I also used 0 to replace the missing value as I assumed that means
no agent. At the last, I used "unknown" to replace the missing values in column "country".</p>


<h3>Converting Imbalance Dataset to Balanced Dataset</h3>
<p>In this dataset, if the room is canceld, then it represents 1, if not it represents 0. By visualizing the count of 1 and 0, I find they have huge defference.
So, I think the dataset is unbalanced, which means one in which the target variable has more observations in one specific class than the others. An unbalanced dataset
may result in poor results, so I merged canceld and non-canced dataset and shffuled them to have a better balanced dataset.</p>

<h1>EDA</h1>
EDA means Exploratory Data Analysis, which is a method that help us understand the dataset quickly and figure out the problems in the dataset.

<h3>Where do the guests come from?</h3>
In this question, I'd like to see which country that most of the guests come from. First, I filter out the data that rooms were cancelled, then counts the number of the guests by coutries.

<h3>How much do guests pay for a room per night?</h3>
<p>In this part, I'd like to see how much the guests pay for different room type per night. To get the total guests, I added up numbers of adult and numbers of child. Then, I diveded the total price by total guest. Also, I calcualte the prices by resort hotel and city hotel seperately. </p>

<h3>How does the price per night vary over the year?</h3>
<p>In this question, I'd like to see how the price vary over the year. So, I used the "adr_pp", which obtained from the last question and the arrival months
to see the trend of the price.</p>

<h3>Which are the most busy month?</h3>
<p>I calculated the guests by different types of hotels, such as city hotel and resort hotel. Also, I found the dataset contains July and August date from 3 years, the other month from 2 years. So, I normalize the data to get the appropriate data for July and August.</p>

<h3>How long do people stay at the hotels?</h3>
<p>To calculate the total nights that the guests stay, I added up two columns, "stays_in_weekend_nights" and "stays_in_week_nights". Then I devided the total nights by the total guests to figure out the average nights that a guest stay.</p>

<h3>Bookings by market segment</h3>
<p>I counts the numbers for different segments to see which channel that most people book rooms.</p>

<h3>How many bookings were canceled?</h3>
<p>Cancellations may cause big impact to hotels, so I'd like to see how many bookings were canceld. So I filtered out the canceld bookings and divided it by the total numbers of bookings.</p>

<h3>Which month have the highest number of cancelations?</h3>
<p>I also checked which month have the highest number of cancellations.</p>

<h1>Predict cancelations</h1>
<h3>Which numerical features are most important?</h3>

<p>I used the correlations to see which features are most important to cancellations.</p>
<h3>Comapring different models</h3>
<li>Seperate features and predicted values:</li>
<p>I added up numerical and category features and set them as x. Then, set the column "is_canceled" as y.</p>
<li>Feature preprocessing:</li>
<p>I used the strategy "constant" to fill the values for numerical features and "unknown" for categorical features.</p>
<li>define models to test:</li>
<p>By utilizing different functions to difine models, I got differe cross validation accuarcy scores for those models. Besides by adjusting parameters of the random forest model, I created a enhanced one to see if the scores could be higher.</p>

<h1>Evaluate Feature importance</h1>
<p>By evaluating the feature importance, we could see which factor may influence the cancellation rates the most.</p>
