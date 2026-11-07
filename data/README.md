# Data

Raw survey responses are **not included** in this repository, to protect respondent privacy.

To run the notebook on real data, add two CSV files here:

- `real_responses.csv`: cleaned Qualtrics export (one row per respondent)
- `synthetic_responses.csv`: LLM-generated responses with the same columns

If these files are missing, the notebook generates a simulated demo dataset instead.

## Expected schema

| Column | Type | Values |
|---|---|---|
| `group` | str | `AI` (treatment) or `Human` (control) |
| `program` | str | Heinz program, e.g. `MISM/MISM-BIDA`, `MSPPM` |
| `age_range` | str | `18-22`, `23-26`, `27-30`, `31+` |
| `sex` | str | `Female`, `Male`, `Prefer not to say` |
| `work_exp` | str | `0-1`, `1-3`, `3-5`, `5+` |
| `career_visit` | str | `Never`, `Once a semester`, `Once a month`, `More than once a month` |
| `ai_pref` | str | `Claude`, `ChatGPT`, `Gemini`, `Other` |
| `credibility` | int | 0 to 10 |
| `expertise` | int | 0 to 10 |
| `quality` | int | 0 to 10 |
| `sharing` | int | 0 to 10 |

## Synthetic data generation

Following the course guidelines, the real sample (n = 85) was given to an LLM, which was prompted to generate 3,000 new rows that statistically resemble the original dataset without copying existing entries. Generated rows were checked for out-of-range values and implausible combinations before analysis.
