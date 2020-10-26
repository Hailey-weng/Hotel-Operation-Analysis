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
<p>In this question, I'd like to see which country that most of the guests come from.</p>
