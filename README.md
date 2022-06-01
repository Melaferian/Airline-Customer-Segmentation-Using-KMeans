# Airline-Customer-Segmentation-Using-KMeans

Customer value has become a major focus among strategy researchers and practitioners as an essential element of a firm’s competitive strategy.
The purpose of this project is to cluster customers. Customer value is seen from various features that provide insights. The results of this clustering will later be used in marketing strategy.

## Data Understanding

There are 62988 rows of data with 23 features which do not have targets/outputs/labels, so in this segmentation case we will use Machine Learning Unsupervised - Clustering.

## EDA

### Univariate Analysis Categorical

![1](https://github.com/Melaferian/Airline-Customer-Segmentation-Using-KMeans/blob/main/Univariate%20Analysis%20Cat.png)

### Univariate Analysis Numeric

![1](https://github.com/Melaferian/Airline-Customer-Segmentation-Using-KMeans/blob/main/Univariate%20Analysis%20Numeric.png)

### Multivariate Analysis

![2](https://github.com/Melaferian/Airline-Customer-Segmentation-Using-KMeans/blob/main/Multivariate%20Analysis.png)


## Feature Selection

Since we will use the RFM model combined with K-Means clustering algorithm, so for the feature selection we will focus on RFM feature. RFM model (R) current consumption time interval, (F) consumption frequency, (M) total consumption identified.

We do this because there are too many attributes in the original data. According to the airline customer value LRFMC model, we only need to select 6 attributes related to the LRMFC indicator: FFP_DATE, LOAD_TIME, FLIGHT_COUNT, AVG_DISCOUNT, SEG_KM_SUM, LAST_TO_END. 


1. **L (Length Relation)** = LOAD_TIME - FFP_DATE

The number of months since the member ’s membership time from the end of the observation window = end time of the observation window-time to join [unit: month]

2. **R (Recency)** = LAST_TO_END

The number of months since the customer ’s most recent flight to the end of the observation window = the time from the last flight to the end of the observation window [Unit: Month]

3. **F (Frequency)** = FLIGHT_COUNT

The number of times the customer took the company aircraft in the observation window = the number of flights in the observation window [Unit: times]
 
4. **M (Monetary)** = SEG_KM_SUM

The accumulated mileage of the customer in the company during the observation period = the total number of flight kilometers in the observation window [Unit: km]

5. **C (Coefficient)** = AVG_DISCOUNT

The average value of the discount coefficients corresponding to the passengers who traveled during the observation period = average discount rate [Unit: None]



## Clustering

![3](https://github.com/Melaferian/Airline-Customer-Segmentation-Using-KMeans/blob/main/Hasil%20Cluster.png)

### Insight

**customer 1 (13421)**

*   A very high L value indicates that customers in this segment are customers who have been with them for a long time.
*   F and M are relative, indicating a reasonably high frequency and flying distance.
*   A low C suggests that customers in this segment are not very interested in promos and fly not because of promos.

**customer 2 (12503)**

*   R in cluster 2 is the highest R value, which means that customers in this segment have not flown for a long time.
*   The low F and M confirm the statement above because the flight frequency and mileage are the lowest.
*   If we look at C or average discount, we can see that customers in this segment are customers who fly because of discounts/promotions.

**customer 3 (10451)**

*   The low L value indicates that the customer in this segment is new.

*   A very low C value indicates that customers in this segment are not customers who fly because of the promo.
*   Low F and M indicate that customers in this segment do not fly often.

**customer 4 (10755)**

*   In this segment, F and M are the highest. The flight frequency and customer mileage in this segment are the highest.
*   If we look at L, L in this segment is the second-largest L, which means that customers in this segment are customers who have been registered for a long time.
*   A low R value indicates that customers in this segment further strengthen the high Frequency and Monetary.

**customer 5 (11930)**
*   A high C value illustrates that customers in this segment are interested because of the promo.
*   And a very low L value, meaning that the customers in this segment are new.
*   F and M indicate that customers in this segment have a reasonably frequent flight frequency.

