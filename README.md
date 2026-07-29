# GIS-Enabled Infrastructure Project Prioritization System

## Overview

This project presents a GIS-enabled Multi-Criteria Decision Making (MCDM) framework developed in Power BI to prioritize urban infrastructure projects in Dammam, Saudi Arabia. The system combines engineering, sustainability, and GIS-based spatial criteria to support transparent and data-driven infrastructure investment decisions.

Unlike traditional project ranking methods that rely solely on cost, this decision-support system evaluates projects across multiple dimensions, including cost, duration, risk, environmental impact, social benefits, economic value, and service gap analysis. Project rankings are dynamically updated based on four different prioritization scenarios.

---

## Problem Statement

Infrastructure projects often compete for limited resources, making prioritization a complex task. Decision-makers must balance engineering feasibility, sustainability goals, and spatial needs when allocating investments.

This project addresses that challenge by developing an analytical model that:

- Evaluates infrastructure projects using multiple criteria.
- Integrates GIS spatial analysis into the decision-making process.
- Supports scenario-based investment planning.
- Provides transparent and explainable project rankings.

---

## Methodology

The prioritization framework consists of three major components:

### Engineering Criteria

- Project Cost
- Project Duration
- Project Risk

### Sustainability Criteria

#### Environmental
- Emission Reduction Potential
- Flood Mitigation Contribution

#### Social
- Service Coverage Improvement
- Equity of Investment

#### Economic
- Lifecycle Cost Efficiency
- Long-Term Economic Benefit

### GIS Spatial Criteria

- Gap Percentage
- Service Gap Analysis
- District-Level Infrastructure Needs

---

## Dataset Preparation

The original GIS dataset only contained spatial information. Additional engineering and sustainability indicators were developed using realistic and representative values based on project types.

The following attributes were added:

| Criteria | Indicators |
|---------|------------|
| Engineering | Cost, Duration, Risk |
| Environmental | Emission Reduction, Flood Mitigation |
| Social | Service Coverage, Equity of Investment |
| Economic | Lifecycle Cost Efficiency, Long-Term Economic Benefit |
| Spatial | Gap Percentage (GIS Analysis) |

The generated values follow logical relationships between project characteristics rather than random assignments.

---

## Data Normalization

Min-Max normalization was applied to standardize all criteria into a common scale.

```
Xnorm = ((X − MIN(X)) / (MAX(X) − MIN(X))) × 10
```

Reference:
> Jiawei Han, Micheline Kamber & Jian Pei, *Data Mining: Concepts and Techniques (3rd Edition), Chapter 3 - Data Processing.*

---

## Priority Score Calculation

The balanced scenario uses the following weights:

| Criteria | Weight |
|---------|--------|
| Engineering | 34% |
| Sustainability | 33% |
| GIS Spatial Gap | 33% |

```
Priority Score =

(Engineering × Weight)
+
(Sustainability × Weight)
+
(Gap Score × Weight)
```

Since lower Engineering scores represent lower cost, duration, and risk, inverse scoring logic is applied where appropriate during scenario calculations.

---

## Scenario-Based Analysis

The system supports four decision-making scenarios.

### Cost Efficiency Scenario

```
((10 - Engineering Score) × 0.70)
+
(Sustainability × 0.15)
+
(Gap Score × 0.15)
```

### Sustainability Priority Scenario

```
((10 - Engineering Score) × 0.15)
+
(Sustainability × 0.70)
+
(Gap Score × 0.15)
```

### Spatial Priority Scenario

```
((10 - Engineering Score) × 0.10)
+
(Sustainability × 0.10)
+
(Gap Score × 0.80)
```

### Balanced Scenario

```
((10 - Engineering Score) × 0.34)
+
(Sustainability × 0.33)
+
(Gap Score × 0.33)
```

Changing the scenario dynamically changes project rankings and investment priorities.

---

## Dashboard Features

The Power BI dashboard includes:

### Executive Overview

- Total Projects
- Total Investment Cost
- Highest Priority Project
- Average Risk Score
- Highest Need District
- GIS Project Distribution Map

### Project Prioritization

- Project Ranking Table
- Priority Score Analysis
- Project Comparison Metrics
- Dynamic Filtering Options

### Scenario Analysis

- Ranking Changes Across Scenarios
- Weight Comparison Analysis
- Scenario Comparison Charts

### Project Details

- Engineering Metrics
- Sustainability Indicators
- Spatial Analysis Results
- Investment Recommendations

---

## Tools & Technologies

- Power BI
- Power Query
- DAX
- GIS Spatial Analysis
- Multi-Criteria Decision Making (MCDM)
- Min-Max Normalization
- Scenario-Based Analysis

---

## References

1. Han, J., Kamber, M., & Pei, J. (2011). *Data Mining: Concepts and Techniques (3rd Edition).* Morgan Kaufmann.

2. MDPI Sustainability Journal:
> *A Scenario-Based Multi-Criteria Decision-Making Approach for Allocation of Pistachio Processing Facilities: A Case Study of Zarand, Iran.*

---

## Project Outcome

This project demonstrates how GIS analytics and Multi-Criteria Decision Making can be integrated to develop an intelligent infrastructure prioritization system. By combining engineering constraints, sustainability objectives, and spatial analysis, the dashboard provides a transparent and flexible framework for supporting infrastructure investment decisions.
