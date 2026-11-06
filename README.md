#  Prediabetes Across Healthcare Systems

## Overview

As a Polish immigrant living in the United Kingdom, I noticed that identical blood test results can sometimes be interpreted differently across healthcare systems.

This project explores how healthcare systems define, identify, classify, and respond to metabolic risk before Type 2 Diabetes develops.

Rather than attempting to determine which healthcare system is "best", the project investigates how different clinical guidelines, diagnostic tests, and intervention pathways influence the identification of prediabetes.

---

## Research Question

**How do different healthcare systems identify, classify, and respond to prediabetes risk?**

---

## Key Insight

During the research phase, it became clear that comparing prediabetes prevalence between countries is far more complex than comparing a single percentage.

Prediabetes statistics may be influenced by:

- Diagnostic thresholds
- Testing protocols
- Fasting requirements
- Clinical guidelines
- Follow-up pathways
- Screening strategies
- Healthcare system structures

This project focuses on understanding how these differences influence the visibility and management of metabolic risk across healthcare systems.

---

## Why This Project?

Type 2 Diabetes is one of the most common preventable chronic diseases worldwide.

As the daughter of a parent with Type 2 Diabetes, and having experienced multiple healthcare systems firsthand, I became interested in understanding:

- When is someone considered "at risk"?
- Which diagnostic tests are used?
- Do countries intervene at different stages?
- What recommendations are provided after risk is identified?
- How consistently is metabolic risk communicated to patients?

---

## Initial Hypotheses

- Prediabetes definitions vary between healthcare systems.
- Countries use different diagnostic tests.
- Testing protocols influence which patients are identified.
- Follow-up recommendations differ significantly.
- Systems may intervene at different stages of disease progression.
- The way risk is measured can influence the resulting statistics.

---

## Countries Included

### MVP Scope

- 🇬🇧 United Kingdom (NICE)
- 🇺🇸 United States (ADA)
- 🇵🇱 Poland (PTD)
- 🇯🇵 Japan (MHLW)

### Potential Future Expansion

- 🇩🇪 Germany
- 🇫🇷 France
- 🇪🇸 Spain
- OECD comparisons
- Historical guideline evolution analysis

---

## Diagnostic Metrics

### HbA1c

Measures average blood glucose over approximately 3 months.

Classifications:

- Normal
- Prediabetes
- Diabetes

### Fasting Plasma Glucose (FPG)

Measures blood glucose levels after an overnight fast.

Classifications:

- Normal
- Prediabetes
- Diabetes

### Oral Glucose Tolerance Test (OGTT)

Measures glucose response following a glucose challenge.

Classifications:

- Normal
- Prediabetes
- Diabetes

---

## Key Business Questions

### Definitions

- How is prediabetes defined in different healthcare systems?
- Which thresholds are used?
- Which tests are recognised by each guideline?

### Testing Protocols

- Which tests require fasting?
- Which tests capture long-term glucose exposure?
- Which tests identify short-term glucose intolerance?

### Clinical Response

- What happens after prediabetes is detected?
- What interventions are recommended?
- How frequently should patients be monitored?

### Healthcare System Comparison

- Do healthcare systems intervene at different stages?
- Do guidelines prioritise different diagnostic methods?
- How does guideline design influence patient pathways?

---

## Data Sources

### United Kingdom

- NICE Guidelines
- NHS Resources

### United States

- American Diabetes Association (ADA)
- CDC Resources

### Poland

- Polish Diabetes Association (PTD)
- Ministry of Health Publications

### Japan

- Ministry of Health, Labour and Welfare (MHLW)
- National Diabetes Guidance Documentation

### Global Sources

- WHO
- OECD

---

# Data Model

## DimCountry

Stores healthcare systems included in the analysis.

Fields:

- CountryID
- CountryCode
- CountryName
- HealthcareSystemType

---

## DimGuideline

Stores clinical guideline information.

Fields:

- GuidelineID
- OrganisationName
- CountryID
- PublicationYear
- DocumentName

Examples:

- NICE
- ADA
- PTD
- MHLW

---

## DimTestingProtocol

Stores testing methodology information.

Fields:

- ProtocolID
- TestType
- FastingRequired
- MeasurementWindow
- Description

Examples:

- HbA1c
- Fasting Plasma Glucose
- OGTT

---

## DimMetric

Stores measurable diagnostic indicators.

Fields:

- MetricID
- MetricName
- StandardUnit
- ProtocolID

Examples:

- HbA1c (%)
- HbA1c (mmol/mol)
- Fasting Plasma Glucose (mg/dL)
- Fasting Plasma Glucose (mmol/L)
- OGTT 2-Hour Glucose (mg/dL)
- OGTT 2-Hour Glucose (mmol/L)

---

## DimClassification

Stores diagnostic classifications.

Fields:

- ClassificationID
- ClassificationName
- ClassificationDescription

Values:

- Normal
- Prediabetes
- Diabetes

---

## FactThreshold

Stores country-specific diagnostic thresholds.

Fields:

- ThresholdID
- CountryID
- GuidelineID
- MetricID
- ClassificationID
- LowerBound
- UpperBound
- Unit
- EffectiveYear

Example:

| Guideline | Metric | Classification | Threshold |
|------------|----------|----------|----------|
| NICE | HbA1c | Prediabetes | 42–47 mmol/mol |
| ADA | HbA1c | Prediabetes | 5.7–6.4% |
| PTD | FPG | Prediabetes | 100–125 mg/dL |
| ADA | OGTT | Prediabetes | 140–199 mg/dL |

---

## FactRecommendation

Stores guideline-specific follow-up actions.

Fields:

- RecommendationID
- CountryID
- GuidelineID
- ClassificationID
- RecommendedAction
- PharmacotherapySuggested
- FollowUpPeriodMonths

Examples:

- Routine Monitoring
- Lifestyle Intervention
- Diabetes Management Plan
- Specialist Referral

---

## Current Implementation Status

### Completed ✅

- Databricks environment configured
- Dimensional data model designed
- Dimension tables implemented
- Fact tables implemented
- Guideline thresholds loaded
- Recommendation model loaded
- Validation queries developed
- Data model tested using SQL joins

### Implemented Tables ✅

#### Dimensions

- DimCountry
- DimGuideline
- DimTestingProtocol
- DimMetric
- DimClassification

#### Fact Tables

- FactThreshold
- FactRecommendation

---

## Technology Stack

### Data Platform

- Databricks
- SQL

### Analytics

- Power BI
- Semantic Modelling

### Supporting Tools

- Python (future enhancement)
- CSV / Excel reference sources

---

## Current Focus

- Expanding threshold coverage
- Validating guideline definitions
- Developing analytical SQL queries
- Designing Power BI semantic model

---

## Planned Dashboard Concepts

### Executive Overview

- Cross-country comparison
- Diagnostic threshold comparison
- Guideline overview

### Testing Protocol Analysis

- Fasting vs non-fasting tests
- Test methodology comparison
- Protocol differences

### Recommendations & Intervention

- Follow-up pathways
- Lifestyle intervention comparison
- Clinical response comparison

### Key Insights

- Similar patients, different classifications
- Diagnostic threshold differences
- Testing protocol differences
- Healthcare system design considerations

---

## Project Objective

This project does not attempt to determine which healthcare system is superior.

Instead, it aims to answer:

**At what point do healthcare systems identify metabolic risk, and what happens next?**

The focus is on understanding how healthcare systems define, measure, communicate, and respond to prediabetes before Type 2 Diabetes develops.
