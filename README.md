# Public Opinion on AI: Measuring Trust, Awareness, and Attitudes

An original survey — designed, fielded, and analyzed end-to-end — measuring
how the American public trusts and perceives artificial intelligence.

See [the full report](./public-opinion-on-ai-report.pdf) for the
complete write-up with weighted toplines and crosstabulations, or the `.qmd`
for the underlying survey design and analysis code.

## Overview

**Research questions:**
- How much trust do people place in AI systems to deliver reliable information?
- What external factors — demographic or experiential — influence that trust?
- What concerns keep people from fully trusting AI systems?

Built a 25-item survey from scratch (research question → sampling plan →
question wording → fielding via Qualtrics), then analyzed the results with
post-stratification weighting to bring the sample in line with national
demographic benchmarks.

## Approach

- **Survey design**: stratified random sampling targeting American adults
  across age, education, gender, race, and prior AI exposure, with older
  adults oversampled to capture generational differences in tech comfort.
- **Instrument**: 25 questions mixing 5-point Likert scales (attitudes) and
  multiple-choice (usage/awareness), sequenced from simple familiarity
  questions into broader attitudes and finally transparency/regulatory
  concerns.
- **Weighting**: raw responses adjusted using post-stratification raking
  weights (`anesrake` in R) across age group, gender, race, Hispanic
  origin, and college education, converging in 37 iterations.
- **Analysis**: weighted topline frequencies plus crosstabulations by age
  group and education level to surface subgroup differences.

## Key findings

- **Knowledge is generationally split**: 63% of 18–25-year-olds and 57% of
  26–34-year-olds rate themselves "Extremely" or "Very" knowledgeable
  about AI, versus just 61% of 55–64-year-olds and 69% of those 65+
  reporting "Not very" or "Not at all" knowledgeable — a clear opportunity
  for targeted AI literacy efforts.
- **Sentiment is mixed-positive, not settled**: 45% agree AI's integration
  into daily life is a good thing overall, 27% disagree, but a sizeable
  28% remain neutral — real ambivalence rather than a firm no.
- **Transparency is close to a baseline expectation**: 78% of respondents
  rate clear explanations of AI decision-making as "Extremely" or "Very"
  important — and this preference is even *stronger* among respondents
  without a college degree (82%) than those with one (76%).
- **Bottom line**: public hesitation about AI reads less like categorical
  rejection and more like a trust gap tied to opacity — one that widens
  along generational and educational lines.

## Repository structure

```
├── public-opinion-on-ai.qmd            # survey design, weighting code, and analysis
├── public-opinion-on-ai-report.pdf     # polished final report: toplines, crosstabs, recommendations
└── README.md
```

## How to run

The full survey instrument, weighting code, and analysis are in the `.qmd`
file. To reproduce the weighting and analysis:

1. You'll need the raw (de-identified) Qualtrics response export — not
   included in this repo to protect respondent data.
2. Install R packages: `dplyr`, `anesrake`.
3. Update the data-loading chunk to point to your response export.
4. Render:
   ```bash
   quarto render public-opinion-on-ai.qmd
   ```

For the results themselves without re-running anything, see
`public-opinion-on-ai-report.pdf`.

## Tools

Qualtrics · R · anesrake (post-stratification raking weights) · survey
design · crosstabulation · Quarto

## Data source

Original data collected via a Qualtrics survey fielded to U.S. adults,
weighted to national demographic benchmarks (age, gender, race, Hispanic
origin, college education).

## Author

Anna Gutierrez — [Portfolio](https://annagtz1.github.io) · [LinkedIn](https://www.linkedin.com/in/anna-gutierrez-m-s/)
