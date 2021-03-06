# Data Biography

## Student Number: **20022308**

---

### 1. Who collected the data?

Murray Cox has collected data on Airbnb from early 2015 via writing a program[1].

---

### 2. Why did they collect it?

Airbnb's data can be used to monitor the data officially released by Airbnb website to prevent them from falsifying data and hiding illegal activities. It can also help tenant rights organizations understand the impact of Airbnb on their cities [2]. Besides, it provides scholars with the data to do some research, such as spatial patterns of peer-to-peer accommodation[3].

---

### 3. How was it collected?

A program was written to collect the data. First, via visiting the Airbnb website's search page, the listings within London are found as much as possible (some inactive listings might be missed). The second step is to visit each listing webpages, and then the details shown on the webpage, including host ID and price, are scraped and write to a file[1].

---

### 4. What useful information does it contain?

This data set shows the information of Airbnb’s listings in London captured on August 24, 2020, with a total of 74188 rows and 74 columns. It contains:

- information of listings - name, longitude and latitude, room type, accommodate, price, minimum and maximum rental term, available days, neighborhood;

- information of reviews - number of reviews, latest and earliest reviews, scores;

- and information of host - ID, name, number of rental houses, location.

---

### 5. What useful information is it missing?

There is some useful but missing information as follows.

- Do they have licenses (null values in the dataset)?

- What are the rental days in the past year? 

- What was the average price in the past month/year? 

- What is the floor area? 

- Do customers need to pay a deposit, and how much? 

---

### 6. To what extent is the data 'complete'?

#### Explore of columns

According to the histogram of the frequency of nullity (Figure 1) and the matrix of the nullity (Figure 2), the degrees of completion in 50 columns are close to 100%, and there are four columns (license, bathrooms, calendar_updated, and neighbourhood_group_cleansed) where the values are all null. However, although the values in bathrooms column are all nullity, it is not missing any data because the information of bathrooms stores in bathrooms_text column. 

#### Explore of rows

Using `isnull` and `describe` function, abnormal rows are found (Table 1). Some key fields, such as latitude and longitude, of the first two rows are all null values. While for the remaining, although both latitude and longitude have values, they are both abnormal values (2).

#### Explore of values

There are total 5415724 values in the data set, of which 644822 is invalid, so the percentage of effective values is 88%, indicating that the values in this data set are relatively complete on the whole scale.

---

### 7. What kinds of analysis would this support?

Columns with few null values are preferred to be selected for research and analysis (Table 2).

#### **Spatial analysis**

Based on location and room type data, it can be used to analyze the different room types' spatial distribution patterns. 

Neighbourhood_cleansed and price columns can be used to analyze the average price in different regions.

Combined minimum_nights and maximum_nights data with location data can identify which areas are mainly for tourism (short-term rental) and which places are mainly for school and work (long-term rental). 

According to calculated_host_listings_count columns and location data, the distribution of Airbnb whose hosts have multiple listings can be analyzed.

#### **Quantitative analysis**

Taking number_of_reviews, accommodates, room_type, minimum_nights, and maximum_nights as independent variables, and price as dependent variables, using appropriate regression model, the correlation between these variables can be found out, as well as the main factors affecting prices.

---

### 8. What kinds of analysis would it _not_ support?

Because of the lack of rental days data, it is impossible to analyze how often an Airbnb listing is being rented out and which listings are the most popular among customers. 

In addition, because of the lack of licenses data, it is unable to identify illegal rentals and find out the relationship between price and illegal rentals.

Last but not least, it is unable to figure out the correlation between price and the floor area, because the latter is missing in the data set.

---

### 9. Which of the uses presented in Q.7 and Q.8 are _ethical_?

When the benefits of prospective data use exceed privacy risks, such use should to be recognized as legal and ethical[4]. Considering this, the ethics of uses listed in #7 and #8 can be discussed as follows. 

First, researching spatial distribution of different room types provides platform to identify the relationship between high Airbnb presence and geographic, demographic, and economic information, which can be used to predict Airbnb's spatial penetration. Considering the expansion of Airbnb may cause the government to suffer losses by effecting revenue of tourism [5], predicting spatial penetration can be a benefit for governments which can help legislators to formulate policies and control the growth of Airbnb [6].

Second, researches such as identifying which areas are mainly for tourism or work and  the most popular region for tourist may help urban planners to have a deeper understanding of regional positioning and development, so as to promote the development of city.

Third, the distribution of Airbnb whose hosts have multiple listings may provide information about area with a lack of regulation. With this information, it is easier to strengthen the supervision of illegal activities and protect the short-term rental market's stability and other hosts' rights and interests.

Therefore, the above several uses for data are ethical because they can bring considerable benefits to social stability and development.

However, the study of the main factors affecting prices may not be ethical. Although it could help researchers understanding the phenomenon of sharing economy accommodation [7], its purpose can also be commercial by providing some commercial hosts with information about factors that are beneficial to increase their personal profits. While the peer-to-peer accommodation intensifies the pressure on the tourism industry in the city center [3]. Therefore, considering the potential risk of the increasing pressure of tourism, although this use may promote development in the field of sharing economy, it cannot be regarded as ethical.

------

### Appendix

**Figure 1:** The frequency of null value

![Figure 1](https://raw.githubusercontent.com/akiakutaji/i2p_assessment/main/Assessment%202%20Data%20Set%20Biography/Figure%20and%20Table/Figure%201%20Frequency%20of%20null%20value.png)

**Figure 2:** The matrix of the nullity

![Figure 2](https://raw.githubusercontent.com/akiakutaji/i2p_assessment/main/Assessment%202%20Data%20Set%20Biography/Figure%20and%20Table/Figure%202%20Matrix.png)

**Table 1:** Abnormal rows 

|       |    id    |                     name                      | latitude | longitude | room_type | accommodates | price | availability_30 | availability_365 |
| :---: | :------: | :-------------------------------------------: | :------: | :-------: | :-------: | :----------: | :---: | :-------------: | :--------------: |
| 3558  | 3138549  |      Heart of City of London/Shoreditch       |   NaN    |    NaN    |    NaN    |     NaN      |  NaN  |       NaN       |       NaN        |
| 29989 | 21549106 | Richmond Luxury, High ceilings & Free Parking |   NaN    |    NaN    |    NaN    |     NaN      |  NaN  |       NaN       |       NaN        |
| 3559  |   NaN    |                       f                       |    2     |     2     |    15     |      2       |   0   |        9        |        9         |
| 29990 |   NaN    |                       f                       |    2     |     2     |   1125    |      2       |  10   |       10        |        10        |

**Table 2:** Information of the columns used as follows

|        Columns   names         | Numbers of null values |  Type   |
| :----------------------------: | :--------------------: | :-----: |
|           room_type            |           2            | object  |
|             price              |           2            | object  |
|       number_of_reviews        |           2            | object  |
|     neighbourhood_cleansed     |           2            | object  |
|         minimum_nights         |           2            | float64 |
|         maximum_nights         |           2            | object  |
|           longitude            |           2            | float64 |
|            latitude            |           2            | float64 |
|            host_id             |           0            | float64 |
| calculated_host_listings_count |           4            | object  |
|          accommodates          |           2            | float64 |

**Code** used in this assessment can be found [here](https://github.com/akiakutaji/i2p_assessment/blob/main/Assessment%202%20Data%20Set%20Biography/Assessment_2_code.ipynb).

------

### Reference

[1]  M. Cox and T. Slee. (2016, Feb. 10) _How Airbnb’s data hid the facts in New York City_ [Online]. Available: http://insideairbnb.com/how-airbnb-hid-the-facts-in-nyc/

[2]  M. Katz. (2017, Feb. 10). _A Lone Data Whiz Is Fighting Airbnb — and Winning_ [Online]. Available:  https://www.wired.com/2017/02/a-lone-data-whiz-is-fighting-airbnb-and-winning/.

[3]  J. Gutiérrez, J. C. García-Palomares, G. Romanillos, and M. H. Salas-Olmedo,  “The eruption of Airbnb in tourist cities: Comparing spatial patterns of hotels and peer-to-peer accommodation in Barcelona,” *Tour. Manag.*, vol. 62, pp. 278–291, Oct. 2017.

[4]  O. Tene and J. Polonetsky, “Privacy in the Age of Big Data: A Time for Big Decisions,” *Stanf. Law Rev. Online*, vol. 64, pp. 63–69, 2014.

[5]  A. Malhotra and M. Van Alstyne, “The Dark Side of the Sharing Economy ... and How to Lighten It,” *Commun. ACM*, vol. 57, pp. 24–27, 2014.

[6]  G. Quattrone, A. Greatorex, D. Quercia, L. Capra, and M. Musolesi, “Analyzing and predicting the spatial penetration of Airbnb in U.S. cities,” *EPJ Data Sci.*, vol. 7, no. 1, p. 31, Dec. 2018.

[7]  C. Gibbs, D. Guttentag, U. Gretzel, J. Morton, and A. Goodwill, “Pricing in the sharing economy: a hedonic pricing model applied to Airbnb listings,” *J. Travel Tour. Mark.*, vol. 35, no. 1, pp. 46–56, Jan. 2018.