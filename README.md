# 📊 A-B Testing of Airbnb's Instant Bookable Feature

The objective of this project is to conduct an A/B test on Airbnb’s 2025 U.S. property listings data to evaluate whether the company’s instant bookable feature leads to an increase in monthly bookings.

# 📌 **Overview**

This project will cover the following:
1. Conduct a high-level analysis of Airbnb's 2025 U.S. property listings by City.
2. Stimulate an A/B Test on the dataset to generate valuable insights on the impact of Airbnb's instant bookable feature.

# 📂 **Datasets**

The datasets used for this project were publicly made available by Airbnb via the [insider Airbnb website](https://insideairbnb.com/get-the-data/)

For this project, I used 2025 Airbnb property listings from **20** major U.S. cities:
- Asheville, NC
- Austin, TX
- Boston, MA
- Chicago, IL
- Columbus, OH
- Dallas, TX
- Denver, CO
- Fort Worth, TX
- Hawaii, HI
- Los Angeles, CA
- Nashville, TN
- New Orleans, LA
- New York City, NY
- Newark, NJ
- Portland, OR
- San Diego, CA
- San Francisco, CA
- Seattle, WA
- Twin Cities, MN
- Washington D.C.

For exploratory data analysis and A/B testing, I primarily focused on **FIVE** variables:
1. id - Listing id.
2. Property Type - Type of listed property.
3. Instant Bookable (True/False) - Whether the property can be instantly booked or not.
4. Reviews per month - Number of reviews the listing had in a month.
5. Listing Location - Name of the city where the listing is located.

# 🔧 **Tools Used**

- **Python** was used for statistical analysis and A/B Testing.
- **Excel** was used for data visualization and exploratory data analysis.

# 📈 **Exploratory Data Analysis**

### 2025 U.S. Airbnb Listings by City — Instant Bookable vs. Non-Instant Bookable

<img width="1396" height="903" alt="image" src="https://github.com/user-attachments/assets/c5982d55-ad91-41ee-ae92-57b32045c5e4" />

### Overall market size and distribution

Los Angeles dominates the U.S. Airbnb market by a significant margin at ~33,500 listings, followed by Hawaii (~26,500) and New York City (~25,000). These three cities collectively dwarf every other market on the chart. From San Diego (~11,000) onwards, there is a steep and fairly steady decline in total listings, with the smallest markets — Fort Worth, Newark — sitting below 4,000 listings each.

### The Non-Instant Bookable dominance

Across virtually every city, Non-Instant Bookable listings (blue) form the majority. This is the structural norm of the U.S. Airbnb market — hosts generally prefer to vet guests before confirming, retaining control over who stays in their property. The pattern holds regardless of market size, geography, or city type.

Hawaii stands out as the most striking outlier — 56% of its listings are Instant Bookable, making it the only market where instant bookings form the majority. This likely reflects a more professionalised, investor-driven host base managing vacation rental properties as a business, where frictionless booking maximises occupancy. San Diego (39%) and Austin (41%) also skew notably higher toward Instant Bookable compared to the national pattern, suggesting similar vacation-market dynamics.

### Key takeaway

The U.S. Airbnb market is overwhelmingly non-instant bookable, but the degree varies meaningfully by city type. Vacation-oriented leisure markets (Hawaii, San Diego, Austin, New Orleans) skew toward instant booking — reflecting professional operators optimising for conversion. Urban residential markets (NYC, Seattle, San Francisco, Portland) skew heavily toward non-instant — reflecting resident hosts who prioritise guest screening. This divide maps closely onto the distinction between short-term rental investment markets and primary-residence sharing markets.

# 🧠 **A/B Test on Airbnb's Property Listings Dataset**

### Features of the A/B Test

- **Null Hypothesis:** Instant Bookable feature does not lead to an increase in a listing's monthly bookings.
- **Alternative Hypothesis:** Instant Bookable feature leads to an increase in a listing's monthly bookings.

This A/B test would consist of two groups:
- **Control:** Listings that don't offer an instant bookable feature to customers.
- **Treatment:** Listings that offer an instant bookable feature to customers.

### Methodology

For the A/B test, I first conducted a t-test on the overall dataset (all 20 cities), followed by separate t-tests for each of the 20 cities. For each t-test, the p-value was calculated to assess statistical significance.

If the p-value for any test was less than 0.05 (indicating statistical significance), I rejected the null hypothesis and concluded that Airbnb’s instant booking feature does indeed lead to an increase in a listing’s monthly bookings in the given location.

### Results

#### Table - Impact of Airbnb's Instant Bookable feature by location.

Key notes:
- Since actual booking numbers weren’t made available by Airbnb, I used reviews per month as a substitute for gross bookings per month — assuming more bookings generally lead to more reviews.
- With reference to the **Diff %** column in the table below, the percentages highlighted in green indicate an increase in the monthly average number of reviews for instantly bookable listings compared to non-instant bookable listings, while those highlighted in red indicate the opposite.
- With reference to the **p-value of T-Test** column in the table below, values greater than 0.05 are highlighed in red (indicating statistical insignificance).

<img width="761" height="739" alt="image" src="https://github.com/user-attachments/assets/8ef4847f-7205-443f-94f6-a2531e0db2cd" />

### Key insights

**1. Strong overall effect**

* Across all cities, instant bookable listings receive **27% more reviews per month (1.76 vs 1.38)**.
* The p-value is **0**, indicating this difference is **statistically significant**.

**2. Positive impact in most cities**

* The majority of cities show **higher reviews for instant bookable listings** (green percentages).
* Some of the largest increases:

  * **New York City**: +141%
  * **San Francisco**: +53%
  * **Los Angeles**: +44%
  * **Austin & Portland**: +41%
* This suggests the feature is particularly impactful in high-demand urban markets.

**3. Statistically significant in nearly all cases**

* Most cities have p-values close to **0**, meaning the observed differences are unlikely due to random variation.
* This strengthens the conclusion that instant booking **genuinely drives higher engagement/bookings**.

**4. Exceptions (no significant effect)**

* **Columbus, OH (p = 0.34)** and **Washington D.C. (p = 0.35)** show **no statistically significant difference**.
* In these cities, the feature does not appear to meaningfully impact booking activity.

**5. Negative impact in a few locations**

* **Hawaii (-12%)** and **Washington D.C. (-3%)** show lower reviews for instant listings.
* However:

  * Hawaii’s result is statistically significant (p = 0), suggesting a real negative effect.
  * Washington D.C.’s result is **not significant**, so no strong conclusion can be drawn there.

### Final takeaway

Airbnb’s instant booking feature **generally leads to higher booking activity**, with statistically significant improvements in most cities. However, its effectiveness **varies by location**, and in rare cases (like Hawaii), it may even have a negative impact.
