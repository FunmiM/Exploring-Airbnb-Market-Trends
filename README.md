# Exploring-Airbnb-Market-Trends

---

# Exploring Airbnb Market Trends (New York City)

## Project Overview

New York City is one of the most visited cities in the world, and Airbnb listings help meet the high demand for short-term and long-term accommodation. In this project, I explored Airbnb listing data from 2019 by combining multiple datasets stored in different file formats.

The goal was to better understand trends in the NYC Airbnb market by cleaning, merging, and analyzing the data.

---

## Dataset Description

This project used three datasets containing information about Airbnb listings:

### **1. `airbnb_price.csv`**

Contains listing price and location details:

* `listing_id`: Unique identifier for each listing
* `price`: Nightly listing price in USD
* `nbhood_full`: Borough and neighborhood where the listing is located

### **2. `airbnb_room_type.xlsx`**

Contains listing descriptions and room types:

* `listing_id`: Unique identifier for each listing
* `description`: Description of the listing
* `room_type`: Room category (shared room, private room, or entire home/apartment)

### **3. `airbnb_last_review.tsv`**

Contains host names and review dates:

* `listing_id`: Unique identifier for each listing
* `host_name`: Name of the listing host
* `last_review`: Date the listing was last reviewed

---

## Tools and Libraries Used

* **Python**
* **Pandas**
* **NumPy**

---

## Methodology / Steps Taken

### **1. Data Importation**

I imported the three datasets using the appropriate methods:

* CSV file using `pd.read_csv()`
* TSV file using `pd.read_csv()` with tab delimiter (`\t`)
* Excel file using `pd.ExcelFile()` and `.parse()`

### **2. Data Merging**

All three datasets were merged into one dataset using `listing_id` as the key column.

### **3. Data Cleaning**

Key cleaning tasks included:

* Converting the `last_review` column into a datetime format
* Sorting the dataset by review date
* Standardizing the `room_type` column by converting values into title case
* Cleaning the `price` column by removing `" dollars"` and converting it into integer values

### **4. Analysis Performed**

After cleaning, I extracted key insights such as:

* The earliest and latest review dates in the dataset
* The total number of listings that are **Private Rooms**
* The average listing price across the dataset

---

## Results / Key Findings

From the cleaned and merged dataset (25,209 entries), I found:

* **Earliest review date:** *May 21, 2019*
* **Latest review date:** *July 05, 2019*
* **Number of Private Rooms:** *11,356*
* **Average price of listings:** *141.78 USD*

---

## Final Output

I summarized the final results into a new dataframe containing:

* `first_reviewed`
* `last_reviewed`
* `nb_private_rooms`
* `avg_price`

This dataframe provides a quick snapshot of Airbnb market activity based on reviews, pricing, and room type distribution.

---

## Conclusion

This project demonstrates how to combine and analyze data stored in multiple file formats (.csv, .tsv, and .xlsx). By merging and cleaning the data, I was able to generate meaningful insights about Airbnb listing activity in New York City in 2019.

