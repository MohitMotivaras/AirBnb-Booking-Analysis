# AirBnb-Booking-Analysis
# **Project Name**    -  AirBnb Booking Analysis



##### **Project Type**    - EDA
##### **Contribution**    - Individual


# **Project Summary -**

In a world where traditional accommodations dominated the hospitality industry, Airbnb emerged as a game-changer, disrupting the way people travel and experience the world. Founded in 2008 by Brian Chesky, Joe Gebbia, and Nathan Blecharczyk, Airbnb quickly became a global phenomenon, connecting travelers with unique and personalized accommodations and creating a new paradigm of collaborative consumption. With a user-friendly platform that facilitated peer-to-peer rentals, Airbnb not only revolutionized the way people booked their stays but also transformed the way homeowners monetized their properties.

The rise of Airbnb can be attributed to several key factors. First and foremost, the platform tapped into a growing demand for authentic, local experiences. Travelers sought alternatives to generic hotel rooms, desiring to immerse themselves in the fabric of a city or a neighborhood. Airbnb's offerings ranged from cozy apartments to eccentric treehouses, giving travelers the opportunity to live like a local, connect with their hosts, and gain insights into the destination beyond the typical tourist attractions.

Furthermore, Airbnb addressed the economic needs of both hosts and guests. Homeowners, often burdened by mortgages or looking for extra income, could leverage their unused or spare spaces by renting them out. This empowered individuals to become micro-entrepreneurs, utilizing their properties as a source of revenue. Guests, on the other hand, benefited from cost-effective accommodations, often at lower prices than traditional hotels, making travel more accessible to a wider range of individuals.

The success of Airbnb was propelled by its innovative digital platform, which prioritized user experience and convenience. The website and mobile application enabled hosts to easily list their properties, upload photos, set prices, and communicate with potential guests. Simultaneously, guests could browse through thousands of listings, filter their searches based on specific preferences, read reviews, and connect directly with hosts for any inquiries. The seamless booking process, combined with robust security measures and a reliable rating system, fostered trust and transparency within the Airbnb community.

Over the years, Airbnb expanded its services beyond accommodations. The company introduced Experiences, a feature that allowed hosts to offer unique activities and guided tours, catering to travelers seeking curated and off-the-beaten-path experiences. By doing so, Airbnb broadened its appeal and provided hosts with additional revenue streams, while guests enjoyed a more holistic and immersive travel experience.

However, Airbnb has not been without its challenges. Critics have raised concerns regarding the impact on local housing markets, gentrification, and the erosion of community ties. Some argue that the rapid growth of Airbnb has led to an increase in housing prices, making it more difficult for locals to find affordable homes. Additionally, the commercialization of residential spaces in popular tourist destinations has sparked debates around the preservation of local culture and the need for regulations to ensure a level playing field.

Despite these challenges, Airbnb has made significant strides in addressing these issues. The company has implemented measures to prevent abuse and unauthorized commercial activities, such as setting limits on the number of nights a property can be rented. It has also collaborated with cities and governments to establish regulations that strike a balance between promoting tourism and protecting local housing markets.

In conclusion, Airbnb has revolutionized the hospitality industry by connecting travelers with unique accommodations, empowering homeowners, and redefining the way people experience travel. With its user-friendly platform, focus on local experiences, and commitment to fostering a global community, Airbnb has become a household name and a symbol of the sharing economy. As the company continues to adapt and navigate challenges, it is poised to shape the future of travel and accommodations, inspiring countless imitators and leaving an indelible mark on the world of hospitality.

# **GitHub Link -**

https://github.com/MohitMotivaras

# **Problem Statement**


Airbnb faces a range of business problems in its booking process, including establishing trust and safety between hosts and guests, maintaining consistent quality standards across diverse listings, ensuring pricing transparency to avoid unexpected costs, resolving disputes between parties efficiently, and navigating complex regulatory and legal requirements across various jurisdictions. These challenges impact user experience, trust, and the overall success of the platform, requiring continuous efforts to improve safety measures, enhance property quality control, provide clearer pricing information, streamline conflict resolution, and adapt to local regulations for sustained growth and customer satisfaction.

#### **Define Your Business Objective?**

**To facilitate seamless and secure transactions between hosts and guests while ensuring trust.**


# **General Guidelines** : -  

1.   Well-structured, formatted, and commented code is required.
2.   Exception Handling, Production Grade Code & Deployment Ready Code will be a plus. Those students will be awarded some additional credits.
     
     The additional credits will have advantages over other students during Star Student selection.
       
             [ Note: - Deployment Ready Code is defined as, the whole .ipynb notebook should be executable in one go
                       without a single error logged. ]

3.   Each and every logic should have proper comments.
4. You may add as many number of charts you want. Make Sure for each and every chart the following format should be answered.
        

```
# Chart visualization code
```
            

*   Why did you pick the specific chart?
*   What is/are the insight(s) found from the chart?
* Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

5. You have to create at least 20 logical & meaningful charts having important insights.


[ Hints : - Do the Vizualization in  a structured way while following "UBM" Rule.

U - Univariate Analysis,

B - Bivariate Analysis (Numerical - Categorical, Numerical - Numerical, Categorical - Categorical)

M - Multivariate Analysis
 ]





# ***Let's Begin !***

## ***1. Know Your Data***

### Import Libraries

# Import Libraries
`import numpy as np`
`import pandas as pd`
`import seaborn as sns`
`import matplotlib.pyplot as plt`

### Dataset Loading

# Dataset Loading

from google.colab import drive
drive.mount('/content/drive')

### Dataset First View

# Dataset First Look

data=pd.read_csv("/content/drive/MyDrive/Classroom/EDA Project/Airbnb NYC 2019.csv")
data.head()

### Dataset Rows & Columns count

# Dataset Rows & Columns count
data.describe

### Dataset Information

# Dataset Info
data.info()

#### Duplicate Values

# Dataset Duplicate Value Count
df = pd.DataFrame(data)

duplicate_count = df.duplicated().sum()

print("Number of duplicate values:", duplicate_count)


#### Missing Values/Null Values

# Missing Values/Null Values Count
data.isnull().sum()

# Visualizing the missing values
missing_values_count = df.isnull().sum()

plt.figure(figsize=(8, 6))
missing_values_count.plot(kind='bar')
plt.title('Missing Values Count')
plt.xlabel('Columns')
plt.ylabel('Number of Missing Values')
plt.xticks(rotation=90)
plt.show()


### What did you know about your dataset?

During the initial analysis of the dataset, it was determined that it contains 48,895 rows and 16 columns. The dataset encompasses various data types, including float64 (3), int64 (7), and object (6). No duplicate values were identified within the dataset. However, certain columns, such as "name," "host name," "last review," and "reviews per month," exhibited null values. In order to facilitate a better understanding of these null values, a graphical representation was created, enabling individuals examining the dataset to gain clearer insights.

## ***2. Understanding Your Variables***

# Dataset Columns

columns = df.columns
columns

# Dataset Describe
data.describe()

### Variables Description

* id: The listing ID of the property.

* host_id: The ID of the host who listed the property.

* latitude: The latitude coordinate of the property's location.

* longitude: The longitude coordinate of the property's location.

* price: The price per night for the property.

* minimum_nights: The minimum number of nights required for a booking.

* number_of_reviews: The total number of reviews for the property.

* reviews_per_month: The average number of reviews per month for the property.

* calculated_host_listings_count: The number of listings the host has.

* availability_365: The number of days the property is available for booking in a year.





### Check Unique Values for each variable.

# Check Unique Values for each variable.
for column in df.columns:
    unique_values = df[column].unique()
    print(f"Unique values for {column}:")
    print(unique_values)
    print()


## 3. ***Data Wrangling***

### Data Wrangling Code

data.isnull().sum()

# Write your code to make your dataset analysis ready.
data.fillna({'reviews_per_month':0}, inplace = True)
data.isnull().sum()

### What all manipulations have you done and insights you found?

Here are the manipulations performed and some insights:

* Handling missing values: The code fills missing values in the 'reviews_per_month' column with 0 using the fillna() function. This ensures that there are no missing values in that column.

* Checking for remaining missing values: The code uses isnull().sum() to check the count of missing values in each column. From the output, it appears that the 'name' column has 16 missing values.

*** Insights: ***

* The 'name' column has 16 missing values that need to be addressed. Depending on the analysis goals and the importance of the 'name' column, you may consider different strategies to handle the missing values. Options could include dropping rows with missing 'name' values, filling the missing values with appropriate data, or imputing the missing values using various techniques.

## ***4. Data Vizualization, Storytelling & Experimenting with charts : Understand the relationships between variables***

#### Chart - 1

# Chart - 1 visualization code
sns.set_palette("muted")
from pylab import *
f, ax = plt.subplots(figsize=(8,6))

subplot(2,3,1)
sns.distplot(data['price'])

subplot(2,3,2)
sns.distplot(data['minimum_nights'])

subplot(2,3,3)
sns.distplot(data['number_of_reviews'])

subplot(2,3,4)
sns.distplot(data['reviews_per_month'])

subplot(2,3,5)
sns.distplot(data['calculated_host_listings_count'])

subplot(2,3,6)
sns.distplot(data['availability_365'])

plt.tight_layout()
plt.show()


##### 1. Why did you pick the specific chart?

* The seaborn library to create six subplots, each displaying a distribution plot (histogram with a kernel density estimate) for different columns in the dataset.

* Charts are suitable for exploring the distribution and patterns within the specific variables/columns in the dataset. They provide insights into the frequency, range, and shape of the data distribution, allowing you to identify potential outliers, understand the central tendency, and discover any patterns or anomalies within the dataset.

##### 2. What is/are the insight(s) found from the chart?

* I observe the following insights from the charts:

Subplot 1: Density plot for 'price':

* This plot visualizes the density distribution of prices.
The y-axis represents the density, indicating the likelihood of different price values occurring. Analyze the shape of the distribution to understand the concentration of prices around certain values.

Subplot 2: Density plot for 'minimum_nights':

* Examine the shape of the distribution to understand the concentration of minimum nights values. Look for modes or clusters to identify common preferences among hosts or guests.

Subplot 3: Density plot for 'number_of_reviews':

* Analyze the shape of the distribution to understand the concentration of review counts. Observe peaks or clusters that might indicate popular or less popular listings.

Subplot 4: Density plot for 'reviews_per_month':

* Examine the shape of the distribution to understand the frequency of reviews. Peaks or clusters might indicate certain activity patterns or trends.

Subplot 5: Density plot for 'calculated_host_listings_count':

* Analyze the shape of the distribution to understand the concentration of listings among hosts. Look for modes or clusters that might indicate active hosts or hosts with a large number of listings.

Subplot 6: Density plot for 'availability_365'

* Examine the shape of the distribution to understand the concentration of availability values. Peaks or clusters might indicate periods of high or low availability.

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

**Positive business impact**
* The gained insights from the distribution charts can potentially help create a positive business impact. Understanding the distribution of prices, minimum stay requirements, number of reviews, and host listings count can provide valuable information for pricing strategies, optimizing minimum stay policies, and identifying high-performing hosts. The insights about availability throughout the year can assist in managing inventory and optimizing occupancy rates. By leveraging these insights, businesses can make data-driven decisions to improve pricing competitiveness, enhance customer experiences, and maximize revenue potential, thereby contributing to a positive business impact.

**Negative growth**
* There is no specific evidence or indication of negative growth in the dataset. However, it's important to note that the charts alone may not provide a comprehensive understanding of the dataset or the factors that could lead to negative growth. Additional analysis and contextual information would be required to make definitive conclusions.

#### Chart - 2

# Chart - 2 visualization code
f, ax = plt.subplots(figsize=(8,6))

subplot(2,3,1)
sns.boxplot(y = data['price'])

subplot(2,3,2)
sns.boxplot(y = data['minimum_nights'])

subplot(2,3,3)
sns.boxplot(y = data['number_of_reviews'])

subplot(2,3,4)
sns.boxplot(y = data['reviews_per_month'])

subplot(2,3,5)
sns.boxplot(y = data['calculated_host_listings_count'])

subplot(2,3,6)
sns.boxplot(y = data['availability_365'])

plt.tight_layout()
plt.draw()


##### 1. Why did you pick the specific chart?

* For following reason i choose this boxplot chart:-
1. Box plots are effective in displaying the distribution of a variable's values, particularly when there are outliers. They provide information about the median, quartiles, and any potential outliers, helping to understand the spread and skewness of the data.
2. By creating a subplot grid, each with a box plot for a different variable, you can easily compare the distributions of these variables side by side. This allows for visual comparisons and identifying any variations or patterns.
3. Box plots are useful for identifying potential outliers in the data. The presence of points outside the whiskers of the box plot indicates values that are significantly different from the rest of the data, potentially warranting further investigation.

##### 2. What is/are the insight(s) found from the chart?

Subplot 1: Box plot for 'price':

* Look for the position of the median line (the horizontal line inside the box) to identify the median price. The box represents the interquartile range (IQR), and the whiskers show the range of the data. Outliers beyond the whiskers might indicate unusually high or low prices.

Subplot 2: Box plot for 'minimum_nights':

* This plot provides insights into the minimum number of nights required for a booking. It helps you understand the typical duration preferred by hosts or guests.

Subplot 3: Box plot for 'number_of_reviews':

* This plot visualizes the distribution of the number of reviews received by listings.Analyze the spread of the box and the presence of outliers to understand the review distribution across listings.

Subplot 4: Box plot for 'reviews_per_month':

* This plot focuses on the rate of reviews per month, indicating the activity level of listings.

Subplot 5: Box plot for 'calculated_host_listings_count':

* Observe the box's spread to gain insights into the distribution of listings among hosts.

Subplot 6: Box plot for 'availability_365':

* This plot shows the availability of listings throughout the year.



##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

**Positive business impact**

Analyzing boxplots can provide insights into the distribution, central tendency, and outliers of each variable. These insights can help businesses make informed decisions and drive positive impacts. For example, by examining the 'price' boxplot, businesses can understand the range of prices and identify any potential outliers. This information can guide pricing strategies, ensuring they are competitive and aligned with market trends. Similarly, insights gained from other variables like 'number_of_reviews' or 'availability_365' can assist in optimizing marketing efforts, improving customer satisfaction, and enhancing overall operational efficiency.

**Negative growth**

I dont have any perticular words for thats why i explain with example
If we observe a decreasing trend or negative growth in the 'number_of_reviews' variable (subplot 2), it may indicate a decline in the number of reviews over time. This could be due to various factors such as decreased customer interest, changes in the platform's popularity, or other external factors impacting the review process.

#### Chart - 3

# Chart - 3 visualization code
df1 = data.groupby('price')['number_of_reviews'].mean().reset_index()
df1

x = df1.loc[:,'number_of_reviews']
y = df1.loc[:,'price']
plt.bar(x, y)
plt.title('Price Vs number_of_reviews')
plt.xlabel('Price')
plt.ylabel('Number_of_reviews')
plt.show()


##### 1. Why did you pick the specific chart?

* To facilitate a comparison between the number of reviews and the price variables, I believe a bar plot would be an effective choice. Bar plots provide a clear and intuitive visualization that allows for a straightforward understanding of the relationship between these two variables. Therefore, I have selected a bar plot as the most suitable chart type for this particular analysis.

##### 2. What is/are the insight(s) found from the chart?

* Based on the bar chart analysis, it appears that the maximum number of reviews is obtained for properties within the price range of 0 to 20. This suggests a significant trend where customers tend to book properties more frequently when the rental prices are lower. Conversely, as the prices increase, there is a noticeable decrease in the number of bookings and subsequently, the number of reviews. This implies a negative correlation between rental price and customer bookings, indicating that higher prices may deter potential customers from making bookings.

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

**Positive business impact**

Offering a range of properties within the 0 to 20 price range can give businesses a competitive advantage. By providing options that cater to budget-conscious customers, they can attract a larger customer base and differentiate themselves from competitors who primarily focus on higher-priced properties.

By capitalizing on the identified price range preference, businesses can explore opportunities to expand into new markets or attract new customer segments. They can develop marketing campaigns targeting budget-conscious travelers and tap into previously untapped customer segments.

**Negative growth**

As rental prices increase, properties may become less affordable for some customers. This can lead to a decrease in demand and, consequently, a decline in bookings.

If alternative properties in the same area or category offer lower prices, customers may choose those options instead. Higher-priced properties may face strong competition from more affordable alternatives, leading to a decline in bookings.


#### Chart - 4

# Chart - 4 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 5

# Chart - 5 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 6

# Chart - 6 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 7

# Chart - 7 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 8

# Chart - 8 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 9

# Chart - 9 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 10

# Chart - 10 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 11

# Chart - 11 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 12

# Chart - 12 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 13

# Chart - 13 visualization code

##### 1. Why did you pick the specific chart?

Answer Here.

##### 2. What is/are the insight(s) found from the chart?

Answer Here

##### 3. Will the gained insights help creating a positive business impact?
Are there any insights that lead to negative growth? Justify with specific reason.

Answer Here

#### Chart - 14 - Correlation Heatmap

# Correlation Heatmap visualization code
corr_matrix = data.corr()


plt.figure(figsize=(10, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm' )


plt.title('Correlation Heatmap')


plt.show()

##### 1. Why did you pick the specific chart?

* The heatmap is particularly useful when you want to explore the relationships between multiple variables. It provides a quick overview of how strongly different variables are related to each other. By using color gradients and annotations, it helps identify both positive and negative correlations.

##### 2. What is/are the insight(s) found from the chart?

* The heatmap provides a visual representation of the correlation strength between different variables. The intensity of the colors indicates the magnitude of the correlation coefficient. Darker colors (such as dark blue or dark red) indicate a stronger correlation, while lighter colors indicate a weaker correlation.

* Lighter colors or squares close to white suggest weak or no correlation between variables. These variables have little or no linear relationship with each other.

* The heatmap allows us to identify the variables that have the strongest correlations. Look for the dark-colored squares, indicating a high correlation coefficient close to 1 or -1. These variables have a strong linear relationship with each other.

#### Chart - 15 - Pair Plot

# Pair Plot visualization code
iris = sns.load_dataset("iris")


sns.pairplot(data=iris, hue="species")


corr_matrix = iris.corr()


for i, j in zip(*np.triu_indices_from(np.ones_like(corr_matrix), k=1)):
    r = corr_matrix.iloc[i, j]
    plt.text(i, j, f"{r:.2f}", ha="center", va="center")


plt.tight_layout()
plt.show()















##### 1. Why did you pick the specific chart?

* The pair plot displays the distribution of each variable on the diagonal axes. This allows us to visualize the spread, skewness, and potential outliers in each variable, providing insights into their individual characteristics.

* The off-diagonal plots are scatter plots that show the relationship between different pairs of variables. By visualizing the data points in this way, we can observe patterns, trends, and potential clusters, which can help in understanding the relationships between variables.

##### 2. What is/are the insight(s) found from the chart?

* The pairplot displays scatter plots for each pair of variables in the Iris dataset, showcasing the distribution and relationship between different features. This provides a quick visual understanding of how the data points are spread across different variables.

## **5. Solution to Business Objective**

#### What do you suggest the client to achieve Business Objective ?
Explain Briefly.

1. Implement a robust verification process for hosts and guests, including identity verification, background checks, and reviews from previous stays.

2. Provide a clear breakdown of pricing components, including base rates, additional fees, and taxes, during the booking process.

3. Gather feedback from users and actively listen to their concerns and suggestions.

# **Conclusion**

 * Airbnb's booking process presents significant challenges related to trust, safety, quality control, pricing transparency, dispute resolution, and regulatory compliance. Addressing these issues is crucial for improving user experience, trust, and platform success. 

### ***Hurrah! You have successfully completed your EDA Capstone Project !!!***
