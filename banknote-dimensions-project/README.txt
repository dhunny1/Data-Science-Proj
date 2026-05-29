Methodology:

We compiled the length and widths for the latest series from wikipedia.org and numista.com.

We included all the currencies that were analyzed in the article "Who's in Your Wallet" (https://pudding.cool/2022/04/banknotes/).

We also included the Euro, West African Franc, Central African Franc, and East Caribbean Dollar.

Here is your **README rewritten without emojis**, clean, professional, and GitHub‑ready.

-----------------------------------------------------------------------------------------------------

# Banknote Dimensions Analysis  
Understanding Global Currency Design Through Data

This project examines how banknote dimensions vary across 42 world currencies. Using Pandas for data cleaning and Matplotlib for visualization, the analysis explores global patterns in currency design, accessibility, and practicality.

---

## Project Overview

Banknotes differ significantly in both length and width across countries. These differences influence:

- Usability, including wallet fit and durability  
- Machine readability for ATMs, vending machines, and counters  
- Accessibility for visually impaired users  

The dataset `banknote-dimensions.csv` includes measurements for banknotes across 22 United Nations subregions.

---

## Dataset

**File:** `banknote-dimensions.csv`  
**Columns include:**

- currency  
- denomination  
- length  
- width  

---

## Key Questions Explored

- Which currencies have the largest differences between their smallest and largest banknotes  
- Which currencies have the largest banknotes overall  
- Whether currencies maintain consistent dimensions across denominations  
- How many currencies:  
  - Keep only length consistent  
  - Keep only width consistent  
  - Have both dimensions vary  
  - Have identical dimensions across all denominations  

---

## Tools and Libraries Used

- Python  
- Pandas for data cleaning, grouping, and aggregation  
- Matplotlib for scatter plots and labeled visualizations  
- Custom helper functions for cleaner charts  

---

## Visualizations

### Paired Scatter Plots
- Longest vs. shortest length per currency  
- Longest vs. shortest width per currency  

### Enhanced Visuals
- Transparency for overlapping points  
- Cleaned axes without spines or tick marks  
- Soft gridlines  
- Consistent point sizing  
- Labels added to highlight currencies and outliers  

---

## Consistency Analysis

The project calculates the percentage of currencies where:

- Only length is consistent  
- Only width is consistent  
- Both dimensions vary  
- Both dimensions are identical  

These results help illustrate global approaches to currency design and accessibility.

---

## Example Output

```
Only length consistent: XX%
Only width consistent: XX%
Both identical: XX%
Both vary: XX%
```

Actual values appear in the notebook output.

---

## Project Structure

```
banknote-dimensions-project/
│── banknote-dimensions.csv
│── banknote-dimensions.ipynb
│── README.md
```

---

## How to Run

1. Clone the repository  
2. Install required Python libraries  
3. Open the notebook  
4. Run all cells  

For Google Colab users, upload the CSV file when prompted.

---

## Summary

This project demonstrates:

- Data cleaning with Pandas  
- Grouping and aggregation  
- Visual storytelling with Matplotlib  
- Real‑world analysis of global currency design  

It serves as a strong example of applied data analysis and visualization skills.

---

If you want, I can also create a matching README for your whale heart rate project or write a resume‑ready project description.
