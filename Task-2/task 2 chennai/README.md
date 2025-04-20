# 🐦 Real-Time Twitter Analytics Dashboard – Power BI - [ TASK -2 ]

This project is part of my Data Analyst Internship at **[NullClass / chennai Internship]**.

## 📝 Task Description

> **Objective:**  
Plot a **scatter chart** to analyze the relationship between **media engagements** and **media views** for tweets that:
- Received **more than 10 replies**
- Have a **word count above 5**
- Were posted on an **odd-numbered date**
- Have an **engagement rate above 5%** (highlighted as "High")
- Chart should only be **visible between 6PM to 11PM IST**

---

## 📁 Project Files

| File | Description |
|------|-------------|
| `Twitter Dashboard.pbix` | Power BI report file containing visuals and DAX logic |
| `tweet.xlsx` | Source data used for analysis |
| `Screenshot (62).png` | Scatter chart not rendering initially |
| `Screenshot (63).png` | Scatter chart setup with filters |
| `Final_Twitter_Dashboard.png` | Final completed dashboard (optional) |

---

## 📌 Key Features Implemented

### ✅ DAX Columns Used

```DAX
-- 1. Word Count
wordCount = LEN(TRIM([Tweet])) - LEN(SUBSTITUTE([Tweet], " ", "")) + 1

-- 2. Tweet Day
Tweet Day = DAY([date])

-- 3. Is Odd Day
IsOddDay = IF(MOD([Tweet Day], 2) = 1, "is odd", "even")

-- 4. Engagement Rate
Engagement Rate = DIVIDE([media engagements], [impressions])

-- 5. Highlight
Highlight = IF([Engagement Rate] > 0.05, "High", "Normal")
```

---

### 📊 Scatter Chart Setup

| Field | Assigned To |
|-------|-------------|
| **X Axis** | `media views` |
| **Y Axis** | `media engagements` |
| **Legend** | `Highlight` |
| **Details** | `Tweet` or `id` |
| **Filters** | `replies > 10`, `wordCount > 5`, `IsOddDay = is odd` |

---

### 🕒 Time Visibility Logic

To control visibility from **6PM to 11PM IST**, created:
```DAX
Tweet Hour = HOUR([time])
```

Then filtered the visual to show only if:
- `Tweet Hour >= 18` and `Tweet Hour <= 23`

Or handled using **Bookmarks + Toggle Buttons**.

---

## 📷 Dashboard Preview

> Final scatter chart and dashboard snapshot

![Dashboard Preview](./Final_Twitter_Dashboard.png)

---

## 📚 Tools Used

- Power BI Desktop
- Microsoft Excel
- DAX (Data Analysis Expressions)
- Visual Filtering & Conditional Display
- Power BI Bookmarks

---

## 📌 Author

**Praveen Gedela**  
Intern @ NullClass /  internship
📍 Chennai , India

---