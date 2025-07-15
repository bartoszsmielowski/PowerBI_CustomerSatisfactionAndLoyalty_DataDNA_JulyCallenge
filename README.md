# 📊 Customer Satisfaction & Loyalty Analytics  
**Power BI Project | DataDNA July Challenge**  
_by Bartosz Smielowski_

---

# 🧑‍💼 Portfolio Note
This project demonstrates:

📈 Advanced Power BI modeling and DAX

🧠 Strategic thinking and business alignment

🎙️ Data storytelling through dynamic commentary

🧼 End-to-end pipeline: cleaning → modeling → insight

Perfect for showcasing analytical depth and communication skills.  

---  

# 🏁 Conclusion  
Customer satisfaction is more than a score — it’s a strategic lens into loyalty behavior and business growth. 
This report delivers clarity, insight, and direction for organizations seeking to improve retention and CX outcomes.

---  


## 🧭 Overview

This Power BI report was developed as part of the **DataDNA July Challenge**, a global initiative focused on data storytelling and visualization excellence.

🎯 **Objective**:  
Identify key drivers of customer satisfaction and loyalty, uncover strategic gaps, and deliver actionable insights for business decision-makers.

👥 **Audience**:  
CX leaders, strategy teams, and executive stakeholders

---


---

## 🗃️ Dataset Summary

The dataset includes customer records with attributes such as:

- Customer Segment (Group A / B)  
- Demographics (Gender, Age Group, Region)  
- Satisfaction ratings across multiple dimensions  
- Loyalty indicator  
- Purchase history

🔍 **Initial Observations**:
- Inconsistent completeness across satisfaction factors  
- Regional skewness in customer distribution  
- Loyalty paradox: returning customers show lower retention

---

## 🧼 Data Preparation (Power Query)

✔️ **Cleaning Steps**:
- Removed duplicates  
- Standardized categorical fields  
- Converted satisfaction scores to decimals  

🔧 **Shaping & Modeling**:
- Built dimension tables such as: `Dim_Satisfaction`, `Dim_Customer`, `Dim_Location`, `Dim_Loyalty`  
- Created fact table: `Fact_CustomerSatisfaction`  
- Merged demographic data for unified analysis

---

## 🧩 Data Model (Power BI)

Implemented a star schema for clarity and performance.

🔗 **Key Measures**:
- `% HighLoyalty`  
- `AvgSatisfaction`  
- `Factor_Correlation_WithFallback`  
- `SR_StrategicNarrativeComment` (dynamic storytelling)

📐 **Model Highlights**:
- Clear relationships between dimensions and fact  
- Modular structure for scalable insights

---

## 📊 Report Pages

### 🟦 Page 1 — Executive Summary  
- Highlights top loyalty drivers: Brand Reputation, Ease of Use, Support Availability  
- Group A shows highest satisfaction and loyalty  
- Loyalty paradox identified among repeat customers

### 🟦 Page 2 — Segment & Region Analysis  
- Regional breakdown of loyalty performance  
- Action panel for targeted retention strategies

### 🟦 Page 3 — Factor Deep Dive  
- Tabular view of satisfaction factors  
- Includes correlation, loyalty %, and strategic recommendations

### 🟦 Page 4 — Strategic Loyalty Drivers  
- Scatter chart showing correlation vs actual retention  
- Commentary highlights strategic gaps (e.g. Brand Reputation)

### 🟦 Page 5 — Tooltip Intelligence  
- Detailed factor-level breakdown  
- Dynamic DAX commentary for each factor

---

## 🧠 Dynamic Commentary (DAX)

A key innovation is the use of **narrative DAX measures** to generate strategic insights:

```dax
SR_StrategicNarrativeComment =
VAR Corr = [# Factor_Correlation_WithFallback]
VAR Loyalty = [% HighLoyalty]
VAR CorrText =
    SWITCH(
        TRUE(),
        Corr >= 0.6, "shows a strong correlation with loyalty",
        Corr >= 0.4, "shows a moderate correlation with loyalty",
        Corr >= 0.2, "shows a weak correlation with loyalty",
        Corr > 0, "shows a very weak correlation with loyalty",
        Corr = 0, "shows no correlation with loyalty",
        Corr < 0, "shows a negative correlation with loyalty"
    )
VAR LoyaltyText =
    SWITCH(
        TRUE(),
        Loyalty >= 0.25, "generates high retention",
        Loyalty >= 0.15, "delivers fair retention",
        Loyalty >= 0.05, "underperforms in actual retention",
        Loyalty < 0.05, "is linked to very low loyalty"
    )

RETURN
    "This factor " & CorrText & " and " & LoyaltyText & 
    ". Focused effort here could help reinforce or unlock loyalty potential."


