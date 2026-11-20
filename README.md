Here is a detailed, easy-to-understand summary of your capstone project report, written in simple language so you can explain every part comfortably during your viva or presentation.

---

### 1. Project Overview & Main Idea

* **Project Title:** *"Which Product Category Receives Higher Ratings?"*


* **Student & University:** Vidhi (Roll No. 2601840017), B.Sc. (Hons.) Data Science at K.R. Mangalam University.


* **What the Project Does:** When people shop online, they often leave star ratings from 1 to 5 after receiving their order. This project studies thousands of clothing reviews to find out **which broad clothing department** (like Tops, Dresses, or Bottoms) and **which specific product type** (like Jeans, Sweaters, or Layering) gets the highest average customer satisfaction.



---

### 2. About the Dataset

* **Dataset Name:** Women's E-Commerce Clothing Reviews (downloaded from Kaggle).


* **Original Size:** It starts with **23,486 rows** (customer reviews) and **11 columns**.
* **Important Columns Used:**
* **Rating:** The customer's star score from 1 (worst) to 5 (best).


* **Department Name:** The main section of the store (6 departments: *Bottoms, Intimate, Jackets, Tops, Dresses, Trend*).


* **Class Name:** The specific clothing item (20 product classes like *Jeans, Layering, Blouses, Pants, Skirts*).


* **Review Text & Recommended IND:** Extra information showing written feedback and whether the buyer recommended the item (`1` = Yes, `0` = No).





---

### 3. Tools & Technologies Used

All the coding and analysis were done inside **Google Colab** using **Python 3**:

* **Pandas:** Used to open the CSV file, clean messy rows, and group ratings by category.


* **NumPy:** Used for basic math and number handling.


* **Matplotlib & Seaborn:** Used to draw clear bar charts showing the results.


* **SciPy:** Used to run a statistical test (the Kruskal-Wallis test) to check if the differences between departments are real or just random luck.



---

### 4. Step-by-Step Working Process (Five Phases)

Your report breaks the project down into five clear phases:

1. **Phase 1 – Defining the Problem:** You decided on the main question: *"Which department and product class receive the highest average ratings?"* and chose the average star rating as the way to measure satisfaction.


2. **Phase 2 – Understanding the Data:** You uploaded the CSV file into Google Colab and checked the column names, data types, and total rows.


3. **Phase 3 – Cleaning & Preparing the Data:** Raw data often has small errors, so you cleaned it before analyzing:


* Removed the extra index column (`Unnamed: 0`).


* Removed **21 duplicate rows** so the same review wasn't counted twice.


* Made sure all ratings were proper numbers between **1 and 5**.


* Removed **14 rows** that had missing department or product class names.


* **Final Clean Dataset:** **23,451 valid reviews** ready for analysis.


4. **Phase 4 – Analyzing & Testing the Data:**
* Calculated the overall average rating and the average rating for every department and product class.


* Applied a **minimum review count rule** ($n \ge 30$) when ranking top product classes so that an item with only 1 or 2 lucky 5-star reviews wouldn't unfairly take first place.


* Ran the **Kruskal-Wallis statistical test** (instead of a standard ANOVA test) because star ratings are heavily skewed toward 5 stars rather than forming a normal bell curve.




5. **Phase 5 – Sharing the Findings:** Summarized the numbers with charts and tables while always showing how many reviews each category had.



---

### 5. Main Results & What They Mean

* **Overall Customer Happiness:**
* The overall average rating across all 23,451 reviews is **4.19 out of 5**.


* More than half of all shoppers (**55.8%**, or 13,097 reviews) gave a full **5 stars**, and **77.5%** gave either 4 or 5 stars. Also, **82.2%** of customers recommended the product they bought.




* **Best Department – Bottoms:**
* **Bottoms** came in first place with an average rating of **4.29 out of 5** across **3,798 reviews**.


* **Intimate** was a very close second (**4.28**, 1,735 reviews), followed by **Jackets** (**4.26**, 1,032 reviews).


* **Tops** had the highest number of reviews (10,455) with an average of **4.17**, **Dresses** averaged **4.15** (6,312 reviews), and **Trend** had the lowest average at **3.82** (119 reviews).




* **Best Product Class – Layering:**
* Among product classes with at least 30 reviews, **Layering** ranked #1 with an average rating of **4.38 out of 5** (146 reviews).


* **Jeans** came right behind at **4.36** (1,146 reviews), followed by **Lounge** (**4.30**, 691 reviews) and **Jackets** (**4.30**, 704 reviews).


* *(Why the minimum count matters: "Casual bottoms" had a 4.50 average, but it only had 2 reviews in the entire dataset—far too small to trust.)*


* **Statistical Test Result (Kruskal-Wallis):**
* **Test Score ($H$):** `79.12` | **p-value:** `1.28e-15` (practically `0.0000`).


* **In Simple Words:** Because the p-value is much smaller than `0.05`, we reject the null hypothesis ($H_0$). This proves that the differences in ratings between departments are **statistically real** and not just due to random chance.





---

### 6. Important Limitations & Future Ideas

* **Limitations (What this study cannot prove):**
* **Correlation, Not Causation:** Just because *Bottoms* have higher ratings does not prove that being a pair of pants *causes* happiness—other factors like fabric, fit, or price could be why.


* **High Ratings $\ne$ High Profit:** A category with high star ratings might still have low total sales or small profit margins.


* **Reviewer Bias & Single Store:** The data comes from just one past women's clothing retailer, and it only includes people who took the time to write a review (silent buyers are not represented).




* **Future Improvements:**
* Use text analysis (**sentiment analysis**) on the written `Review Text` to learn *why* people gave 1 star or 5 stars (for example, complaining about sizing vs. praising comfort).


* Include product prices, discounts, and confidence intervals to make the business insights even stronger.
