# Data Professional Survey – Power BI Dashboard

A Power BI project where I take a survey of 630 data professionals, clean it in Power Query and build a one-page dashboard to see who works in data, what they earn, how happy they are and how hard it was to get into the field.

---

## Dataset

A survey of data professionals with questions on job title, salary, industry, favourite programming language, happiness at work, how difficult it was to break into data, age, gender, country and education.

## Tools

- Power BI Desktop
- Power Query (data cleaning and transformation)

---

## Data cleaning (Power Query)

- **Removed columns I didn't need** (Browser, OS, City, Country, Referrer).
- **Tidied up the "Other" answers:** for questions where people could write their own answer, the text came after "Other (please specify)". I split these columns on `(` or `:` and only kept the first part, so all free-text answers are grouped as **Other**. This was done for job title, favourite programming language, industry and country.
- **Turned the salary ranges into numbers:** salary came as text ranges like `41k-65k`, so I:
  - duplicated the column so I keep the original
  - split it into a low and a high number
  - removed the `k` and `-`
  - replaced `225k+` with `225` so it has a number
  - created an **Average Salary** column = (low + high) / 2
- **Set the correct data types** (numbers, text, dates).

## Dashboard

| Visual | What it shows |
|--------|---------------|
| Cards | Number of survey takers and their average age |
| Treemap | Where survey takers live |
| Bar chart | Average salary by job title |
| Stacked column chart | Favourite programming language, split by job title |
| Gauges | Average happiness with work/life balance and with salary (0–10) |
| Donut chart | How difficult it was to break into data |

## Findings

- **630 people** took the survey, with an **average age of about 30**.
- Most were from the **United States** (261), then **India** (73), the **UK** (40) and **Canada** (32).
- **Data Analysts were by far the biggest group** (381 out of 630, 60%).
- **Data Scientists earn the most**, around **$94k** on average, compared to $65k for Data Engineers and $55k for Data Analysts. (Data Architects look high too, but there were only 3 of them, so that number isn't reliable.)
- **Python is the clear favourite** (420 votes, 67%), then R (101).
- People are **less happy with their salary (4.3/10)** than with their **work/life balance (5.7/10)**.
- **Breaking into data:** 43% said it was neither easy nor difficult, but **almost a third (32%) found it difficult or very difficult**, compared to 26% who found it easy.

## What I learned

- Power Query keeps every cleaning step recorded, so I can always see or undo what I did.
- Survey data needs a lot of tidying, especially free-text answers and ranges stored as text.
- Turning salary ranges into an average gives a number I can actually do maths on, but it's an estimate, not the real salary.
- Small groups (like 3 Data Architects) can make averages look misleading.

## How to open it

Download the `.pbix` file and open it in Power BI Desktop. If you want to refresh the data, download the Excel file too, then in Power BI go to **Transform data → Data source settings** and point it to where you saved the file.

## Credit

This project follows the Power BI portfolio project from [Alex The Analyst's](https://www.youtube.com/@AlexTheAnalyst) Data Analyst Bootcamp.
