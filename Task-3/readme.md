# 🐦 Real-Time Twitter Analytics Dashboard – Power BI - [ TASK -3 ]

This repository contains a Power BI project developed as part of my **Data Analyst Internship at NullClass**. The project focuses on analyzing Twitter engagement metrics with dynamic controls based on **system time** and **manual toggle** inputs.

---

## 📁 Project Structure

| File Name                    | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `Twitter Dashboard.pbix`    | Main Power BI report file                                 |
| `Tweet.xlsx`                | Raw Twitter data used as the source                       |
| `Dashboard_Screenshot.png`  | Full screenshot of the interactive dashboard              |
| `LineChart_Visibility.png`  | Example of graph visibility based on system/manual toggle |
| `README.md`                 | Documentation and overview of the project                 |

---

## 🧠 Features

- **Line Chart** showing average engagement rate per month
- Filters based on:
  - Tweet Date (odd)
  - Engagement Count (even)
  - Tweet Length (> 20 characters)
  - Exclusion of tweets containing the letter **‘C’**
- **Two visibility control options** for the chart:
  1. **Manual Toggle (Button)**
  2. **System Time Based Visibility**
- **Message Display** when the chart is hidden
- Current system time displayed dynamically

---

## 🛠️ DAX Logic Used

### 🔹 Columns Created:

```dax
HourIST = HOUR('SocialMedia (1)'[time]) + 5

CharacterCount = LEN('SocialMedia (1)'[Tweet])

IsOddDate = MOD(DAY('SocialMedia (1)'[time]), 2)

IsEngagementEven = MOD('SocialMedia (1)'[engagements], 2)

remove_C_fromTweet = IF(CONTAINSSTRING(LOWER('SocialMedia (1)'[Tweet]), "c"), 1, 0)
```

### 🔹 Measures Created:

```dax
ShowGraphControl =
VAR ManualToggle = SELECTEDVALUE(TimeToggle[ShowChart]) = "Yes"
VAR CurrentHour = HOUR(NOW())
VAR TimeCondition =
    (CurrentHour >= 7 && CurrentHour <= 11) ||
    (CurrentHour >= 15 && CurrentHour <= 17)
RETURN
    IF(ManualToggle || TimeCondition, 1, 0)
```

```dax
GraphNoticeText =
VAR ManualToggle = SELECTEDVALUE(TimeToggle[ShowChart]) = "Yes"
VAR CurrentHour = HOUR(NOW())
VAR TimeCondition =
    (CurrentHour >= 7 && CurrentHour <= 11) ||
    (CurrentHour >= 15 && CurrentHour <= 17)
RETURN
IF(
    ManualToggle || TimeCondition,
    BLANK(),
    "❌ This visual is only available between 3 PM – 5 PM IST & 7 AM – 11 AM IST"
)
```

---

## 📸 Dashboard Preview
![image alt](https://github.com/Gedelapraveen/Twitter_Dashboard_Real-Analytics_DataAnalysis/blob/main/Task-3/task_3chennai/Screenshot%20(66).png?raw=true)

---

## 🚀 How to Use

1. Clone or download the repository
2. Open `Twitter Dashboard.pbix` in Power BI Desktop
3. Make sure `Tweet.xlsx` is in the same folder path
4. Explore the visuals and toggle options

---

## 📬 Contact

Feel free to connect with me on [LinkedIn](#) or reach out via email if you have questions.

---

## 🏅 Internship Details

**Internship by**: NullClass  
**Duration**: 26-03-2025 to 26-04-2025  
**Role**: Data Analyst Intern  
**Project**: Real-Time Twitter Analytics Dashboard

📌 Author
Praveen Gedela
Intern @ NullClass / AVC IT Solutions
📍 Hyderabad, India



---
