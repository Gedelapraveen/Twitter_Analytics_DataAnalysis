
# 📊 Real-Time Twitter Analytics Dashboard – nullclass

This repository includes three internship tasks completed during my **Data Analyst Internship at NullClass**, focused on Twitter data analysis using **Power BI** and **DAX**.

---

## ✅ Task Summaries

### 🔹 Task 1 – Avg Engagement & Impressions
**Objective:** Create visuals showing average engagement rate and total impressions for tweets with:
- Likes = 0
- Impressions ≥ 100
- Date: 01-Jan-2020 to 30-Jun-2020
- Time: 3 PM – 5 PM IST

**Files:**
- `Twitter Analytics Dashboard_[Task-1].pbix`
- `Tweets.xlsx`
- `visual_screenshot.png`

---

### 🔹 Task 2 – Scatter Chart Analysis
**Objective:** Scatter chart of media engagements vs. media views for tweets that:
- Have > 10 replies
- Word count > 5
- Are on odd-numbered days
- Engagement rate > 5%
- Time: 6 PM – 11 PM IST

**DAX Columns:**
- `wordCount`: Count of words in Tweet
- `Tweet Day`: Extract day from date
- `IsOddDay`: Check if tweet date is odd
- `Engagement Rate`: media engagements / impressions
- `Highlight`: If engagement > 0.05

**Filters:** replies, wordCount, IsOddDay

**Files:**
- `Twitter Dashboard.pbix`
- `tweet.xlsx`
- `Screenshot (62).png`
- `Screenshot (63).png`
- `Final_Twitter_Dashboard.png`

---

### 🔹 Task 3 – Line Chart with Visibility Control
**Objective:** Show average engagement by month, visible only at specific hours or with a manual toggle. Exclude tweets with:
- Tweet length ≤ 20
- Even tweet date
- Engagement count not even
- Tweets with character 'C'

**DAX Columns:** HourIST, CharacterCount, IsOddDate, IsEngagementEven, remove_C_fromTweet  
**DAX Measures:** ShowGraphControl, GraphNoticeText

**Files:**
- `Twitter Dashboard.pbix`
- `Tweet.xlsx`
- `Dashboard_Screenshot.png`
- `LineChart_Visibility.png`

---

## 💻 Tools Used
- Power BI Desktop
- Microsoft Excel
- DAX (Data Analysis Expressions)
- Visual Filtering & Conditional Display
- Power BI Bookmarks

---

## 👤 Author

**Gedela Praveen**  
Intern @ NullClass, Chennai  
📍 India

---
