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

## 💬 Example Prompts

### **Basic factual**
