# 🩸 Prediabetes Across Healthcare Systems

## Overview

As a Polish immigrant living in the United Kingdom, I noticed that identical blood test results can sometimes be interpreted differently across healthcare systems.

This project explores how different countries define, identify, and communicate prediabetes risk, with a focus on early intervention and prevention of Type 2 Diabetes.

Rather than assuming one healthcare system is better than another, the goal is to understand how different systems approach metabolic risk and at what point they begin to act.

---

## Research Question

**How do different healthcare systems identify and communicate prediabetes risk?**

---

## Why This Project?

Type 2 Diabetes is one of the most common preventable chronic diseases worldwide.

As the daughter of a parent with Type 2 Diabetes, and having experienced different healthcare systems firsthand, I became interested in understanding:

- When does a healthcare system decide someone is "at risk"?
- How is that risk communicated?
- What happens after potential risk is identified?
- Do different countries intervene at different stages?

---

## Initial Hypotheses

- Prediabetes thresholds differ between countries.
- Healthcare systems vary in how they communicate metabolic risk.
- Some systems intervene earlier than others.
- Follow-up pathways differ significantly between healthcare systems.
- Historical changes may be as important as current differences.

---

## Countries Included

### MVP Scope

- 🇬🇧 United Kingdom
- 🇵🇱 Poland
- 🇺🇸 United States

### Possible Future Expansion

- 🇯🇵 Japan
- 🇩🇪 Germany
- 🇫🇷 France
- 🇪🇸 Spain
- OECD comparisons

---

## Metrics

### HbA1c

- Normal
- Prediabetes
- Diabetes

### Fasting Blood Glucose

- Normal
- Prediabetes
- Diabetes

### Oral Glucose Tolerance Test (OGTT)

- Normal
- Prediabetes
- Diabetes

---

## Key Questions

### Definitions

- How is prediabetes defined in each country?
- Are thresholds consistent across healthcare systems?
- Which diagnostic tests are used?

### Communication

- How is risk communicated to patients?
- Has the language changed over time?
- Are patients actively informed about future diabetes risk?

### Intervention

- What happens after a prediabetes diagnosis?
- Are structured prevention programmes available?
- How often are follow-up tests recommended?

### Trends Over Time

- How have definitions changed?
- When was HbA1c adopted as a diagnostic tool?
- Have countries become more or less aggressive in early detection?

---

## Data Sources

### United Kingdom

- NICE Guidelines
- NHS Resources

### Poland

- Polish Diabetes Association (PTD)
- Ministry of Health publications

### United States

- American Diabetes Association (ADA)
- CDC

### Global Sources

- WHO
- OECD

---

## Proposed Data Model

### DimCountry

- CountryID
- CountryName
- HealthcareSystemType

### DimMetric

- MetricID
- MetricName
- Unit

Examples:

- HbA1c
- Fasting Glucose
- OGTT

### DimGuideline

- GuidelineID
- Organisation
- Country
- PublicationYear

Examples:

- NICE
- ADA
- PTD
- WHO

### FactThreshold

- CountryID
- MetricID
- GuidelineID
- LowerBound
- UpperBound
- Classification
- EffectiveYear

Examples:

- Normal
- Prediabetes
- Diabetes

### FactRecommendation

- CountryID
- GuidelineID
- Classification
- RecommendedAction
- FollowUpPeriod

---

## Dashboard Concepts

- Country comparison
- Threshold comparison
- Timeline of guideline changes
- Prediabetes patient journey
- Early intervention comparison
- Key insights and conclusions

---

## Technology Stack

- SQL
- Power BI
- Semantic Model
- Microsoft Fabric
- Python (optional)
- Excel / CSV data sources

---

## Project Objective

This project does **not** aim to determine which healthcare system is "best".

Instead, it aims to answer:

> **At what point do healthcare systems identify metabolic risk, and what happens next?**

The focus is on understanding how healthcare systems define, communicate and respond to prediabetes before Type 2 Diabetes develops.

---

## Project Status

🟡 Planning Phase

Current activities:

- Defining scope
- Identifying data sources
- Designing data model
- Preparing comparison framework
