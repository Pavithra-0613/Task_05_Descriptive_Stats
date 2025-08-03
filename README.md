# Task_05_Descriptive_Stats
Research Task 5 for OPT — Using Syracuse Women's Lacrosse 2023 stats to test LLM question answering accuracy with descriptive statistics

## 📌 Project Overview
This project is part of **OPT Research Task 5** for the Syracuse University iSchool OPT program.  
The goal is to test the ability of Large Language Models (LLMs) — such as ChatGPT, Claude, or GitHub Copilot — to correctly answer natural language questions about a small, structured dataset.  

For this task, I used the **Syracuse Women's Lacrosse 2023 Season Stats** dataset.

---

## 📂 Dataset
**Source:** [Syracuse Women's Lacrosse Statistics](https://cuse.com/sports/2013/1/16/WLAX_0116134638)  
**Format:** CSV (Cleaned)  
**Columns:**
- Player – Player name
- GP – Games Played
- G – Goals
- A – Assists
- Pts – Points
- Sh – Shots
- Gw – Game-Winning Goals
- GB – Ground Balls
- DC – Draw Controls
- TO – Turnovers
- CT – Caused Turnovers

⚠️ **Note:** Original dataset was in PDF format. Cleaned and converted to CSV before use.

---

## 🛠️ Methodology
1. **Data Cleaning**
   - Extracted table from PDF.
   - Removed unnecessary rows/columns.
   - Reformatted into clean CSV with one row per player.
   
2. **Validation**
   - Used basic descriptive statistics in Python/Excel to find correct answers for:
     - Top scorer (Goals)
     - Most assists
     - Most points
     - Most possession impact (GB + DC)
     - Most defensive impact (CT)

3. **LLM Prompting**
   - Provided dataset to the LLM.
   - Asked both simple factual and complex judgment questions.
   - Compared LLM responses to validated statistics.

---

## 💬 Example Prompts & Correct Answers

Below are examples of the types of questions asked to the LLM, along with the correct answers from the dataset for validation.

---

### **Basic Factual Prompts**
1. **Who scored the most goals?**  
   ✅ *Megan Carney – 59*

2. **Which player had the most assists?**  
   ✅ *Emma Ward – 56*

3. **Who had the highest total points?**  
   ✅ *Meaghan Tyrrell – 107*

4. **Who had the most caused turnovers?**  
   ✅ *Katie Goodale – 27*

---

### **Intermediate Prompts**
5. **Which player contributed most to possession (GB + DC)?**  
   ✅ *Olivia Adamson – 114*

6. **Which player had the highest shooting efficiency (Goals ÷ Shots)?**  
   ✅ *Katelyn Mashewsk – 1.00* (scored on every shot attempted)

---

### **Complex Judgment Prompts**
7. **If the coach wants to win two more games next season, should the focus be on offense or defense? Which one player should be prioritized, and why?**  
   ✅ *Likely focus: Defense* – While the team scores well, improving defensive control and reducing opponent scoring could yield more wins.  
   **Recommended player:** *Katie Goodale* – Leads in caused turnovers (27) and is key for disrupting opponents’ possession.

---

## 📊 LLM Test Results

| Question | Correct Answer (Dataset) | LLM Response | Correct? |
|----------|--------------------------|--------------|----------|
| Who scored the most goals? | Megan Carney – 59 | Meaghan Tyrrell | ❌ |
| Which player had the most assists? | Emma Ward – 56 | Emma Ward | ✅ |
| Who had the highest total points? | Meaghan Tyrrell – 107 | Meaghan Tyrrell | ✅ |
| Who had the most caused turnovers? | Katie Goodale – 27 | Emma Tyrrell | ❌ |
| Which player contributed most to possession (GB + DC)? | Olivia Adamson – 114 |  |  |
| Which player had the highest shooting efficiency (Goals ÷ Shots)? | Katelyn Mashewsk – 1.00 |  |  |
| If the coach wants to win two more games next season, should the focus be on offense or defense? Which one player should be prioritized, and why? | **Likely:** Defense – Katie Goodale (to reduce turnovers & improve possession) |  |  |

---

## 🔗 LLM Test Conversation Link
[View ChatGPT Conversation](https://chatgpt.com/share/688eb41c-1e5c-8005-b5b6-dc09dcd6e995)


## 📈 Observations

After running the prompts through the LLM and comparing them to the validated dataset answers, the following observations were made:

1. **Basic factual questions** (e.g., top scorer, most assists) were generally answered correctly by the LLM when the dataset was presented in a clear tabular format.
2. **Intermediate questions** (e.g., possession leader, shooting efficiency) required the LLM to perform calculations. Accuracy varied depending on whether the LLM interpreted column definitions correctly.
3. **Complex judgment questions** (e.g., strategy to win more games) were subjective and depended on how the prompt was framed. LLMs tended to make reasonable recommendations but sometimes focused on star players rather than using calculated metrics.
4. The LLM occasionally confused **similar statistical categories** (e.g., total points vs. goals) if column names were not explained clearly in the prompt.
5. **Prompt clarity** greatly improved accuracy. Explicitly stating how to calculate a metric (e.g., “add Ground Balls + Draw Controls”) increased the likelihood of correct results.
6. The LLM performed best when the dataset was **small and fully visible** in the conversation context, allowing it to scan all rows and compute without relying on memory.

**Overall takeaway:**  
LLMs can reliably answer straightforward questions from well-structured datasets, but for complex analysis or multi-step calculations, prompts should be explicit and results should always be validated against actual statistics.
