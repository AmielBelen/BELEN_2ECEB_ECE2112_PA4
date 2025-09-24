# Experiment 4 - Data Wrangling and Data Visualization  

This repository contains my solution for **Experiment 4** in Advanced Computer Programming and Algorithms.  

The experiment focuses on **using Pandas for data wrangling and visualization**, specifically on filtering datasets, creating subsets, and presenting results through visual storytelling.  

---

## Table of Contents  
- [Problem 1](#problem-1)  
- [Results](#results)  

---

### Code Files  
- [View Jupyter Notebook](./BELEN_Experiment%204.ipynb)  
- [Dataset](./board2.xlsx)  

---

## Problem 1  

In this problem, I was required to perform **data wrangling** on the dataset (`board2.xlsx`), which contains student records including their name, gender, track, hometown, and grades in Math, Electronics, GEAS, and Communication.  

The task was divided into two parts:  

---

#### 1. Data Wrangling  

- **Instru DataFrame**: Selected students who belong to the *Instrumentation* track, have hometown *Luzon*, and scored greater than 70 in Electronics.  

```python
Instru = df[
    (df["Track"] == "Instrumentation") &
    (df["Hometown"] == "Luzon") &
    (df["Electronics"] > 70)
][["Name", "GEAS", "Electronics"]]
```

- **Mindy DataFrame**: Selected *Female* students from *Mindanao* with an average grade greater than or equal to 55.  

```python
Mindy = df[
    (df["Hometown"] == "Mindanao") &
    (df["Gender"] == "Female") &
    (df["Average"] >= 55)
][["Name", "Track", "Electronics", "Average"]]
```

---

#### 2. Data Visualization  

Three bar charts were created to analyze how different features contribute to the average grade:  

- **Average Grade by Track**  
```python
df.groupby("Track")["Average"].mean().plot(kind="bar", title="Average Grades by Track")
```

- **Average Grade by Gender**  
```python
df.groupby("Gender")["Average"].mean().plot(kind="bar", title="Average Grades by Gender")
```

- **Average Grade by Hometown**  
```python
df.groupby("Hometown")["Average"].mean().plot(kind="bar", title="Average Grades by Hometown")
```

---

### Conclusion  

The analysis shows that average grades vary more by Track, with smaller differences by Gender and moderate variation by Hometown, suggesting Track has the strongest influence on student performance.  

---

## Results  

- **Instru DataFrame**: Displayed Instrumentation students from Luzon with Electronics > 70.  

- **Mindy DataFrame**: Displayed Female students from Mindanao with Average ≥ 55.  

- **Visualizations**: Showed comparisons of average grades by Track, Gender, and Hometown.  

- **Conclusion**: Provided a concise interpretation of which feature contributes most to differences in student performance.  

---

✨ This experiment demonstrates how **data wrangling** and **visualization** can be combined with **storytelling** to interpret dataset insights effectively.  
