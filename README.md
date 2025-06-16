# 🧾 Retail Data Analysis with Pandas – Python & Google Colab

This project demonstrates how to clean, transform, and analyze a small retail dataset using **Pandas** in **Python**. The exercise focuses on creating a DataFrame from a list of dictionaries and performing various operations such as renaming columns, data type conversion, arithmetic calculations, and rounding.

---

## 📌 Project Overview

The exercise involves analyzing sales data of retail products like USB cables, batteries, and a wireless mouse. Each product record contains:
- Product name
- Price (as string)
- Type
- Units sold (manually added)

The goal is to clean the data and compute the **total revenue** for each product.

---

## 🛠 Tools Used

| Tool           | Purpose                          |
|----------------|----------------------------------|
| **Python** 🐍        | Core programming language |
| **Pandas** 📊        | Data manipulation and analysis |
| **Google Colab** 💻  | Cloud-based Jupyter notebooks |

---

## 🎯 Objectives

1. Create a DataFrame from a list of dictionaries
2. Rename a column to improve naming consistency
3. Add a new column with units sold
4. Convert a price string to float
5. Calculate total revenue per product
6. Round the total revenue to the nearest whole number

---

## 🔍 Exercise Breakdown

### 🧱 Step 1: Define the Dataset
```python
items = [
  {"item name": "USB cable", "price": "$10.99", "type": "USB C to USB C"},
  {"item name": "USB cable", "price": "$10.99", "type": "USB A to USB C"},
  {"item name": "Batteries", "price": "$9.99", "type": "AA"},
  {"item name": "Batteries", "price": "$8.99", "type": "AAA"},
  {"item name": "Mouse", "price": "$12.99", "type": "Wireless USB"},
]
# 📟 Retail Data Analysis with Pandas – Python & Google Colab

This project demonstrates how to clean, transform, and analyze a small retail dataset using **Pandas** in **Python**. The exercise focuses on creating a DataFrame from a list of dictionaries and performing various operations such as renaming columns, data type conversion, arithmetic calculations, and rounding.

---
## 🔍 Exercise Breakdown

### 🧱 Step 1: Define the Dataset

```python
items = [
  {"item name": "USB cable", "price": "$10.99", "type": "USB C to USB C"},
  {"item name": "USB cable", "price": "$10.99", "type": "USB A to USB C"},
  {"item name": "Batteries", "price": "$9.99", "type": "AA"},
  {"item name": "Batteries", "price": "$8.99", "type": "AAA"},
  {"item name": "Mouse", "price": "$12.99", "type": "Wireless USB"},
]
df = pd.DataFrame(items)
```
![image](https://github.com/user-attachments/assets/5a47d115-804f-4e3c-939f-a9f11db5f149)


### 🖊️ Step 2: Rename the Column

```python
df.rename(columns={"item name": "item_name"}, inplace=True)
```
![image](https://github.com/user-attachments/assets/d2893174-7b7e-4a9c-869b-fb18452bb7a5)


### ➕ Step 3: Add Units Sold

```python
df["units_sold"] = [41, 113, 54, 35, 22]
```
![image](https://github.com/user-attachments/assets/775b24e0-5b10-447c-bd87-193e4e4d4844)


### ↓ Step 4: Convert Price Column to Float

```python
df["price"] = df["price"].str.replace("$", "", regex=False).astype(float)
```
![image](https://github.com/user-attachments/assets/6448ecf5-3767-44e1-9ccf-5a502f6caa55)
![image](https://github.com/user-attachments/assets/bee357e6-444b-43ca-9c1b-2ebe9c46d96f)
![image](https://github.com/user-attachments/assets/288d2191-6fae-474b-8578-c054694e0d2c)




### 💰 Step 5: Calculate Total Revenue

```python
df["total_revenue"] = df["price"] * df["units_sold"]
```
![image](https://github.com/user-attachments/assets/0adb853f-a41f-43b5-9570-42ea073f60f4)


### ✅ Step 6: Round Revenue

```python
df["total_revenue"] = df["total_revenue"].round().astype(int)
```
![image](https://github.com/user-attachments/assets/9cf2e5d4-0923-499a-aa39-277c4f2af2ab)


---

## 📊 Final Output Table

![image](https://github.com/user-attachments/assets/e59871f2-ff3c-43bc-859d-5aacf8ad4daa)


| item\_name | price | type           | units\_sold | total\_revenue |
| ---------- | ----- | -------------- | ----------- | -------------- |
| USB cable  | 10.99 | USB C to USB C | 41          | 451            |
| USB cable  | 10.99 | USB A to USB C | 113         | 1242           |
| Batteries  | 9.99  | AA             | 54          | 539            |
| Batteries  | 8.99  | AAA            | 35          | 315            |
| Mouse      | 12.99 | Wireless USB   | 22          | 286            |

---

## 📅 Conclusions

* ✅ String cleaning is essential for numerical computations.
* ✅ Pandas enables efficient arithmetic operations across series.
* ✅ You can chain transformations for concise and readable code.
* ✅ This exercise demonstrates foundational data cleaning and engineering steps.

> ✨ Ideal for beginners exploring data manipulation with Pandas in real-world scenarios!

