# 📊 Customer Satisfaction & Loyalty Analytics  
**Power BI Project | DataDNA July Challenge**  
_by Bartosz Smielowski_  


![CustomerSatisfactionLoyalty](https://github.com/bartoszsmielowski/PowerBI_CustomerSatisfactionAndLoyalty_DataDNA_JulyCallenge/blob/main/003%20Multimedia/CustomerSatisfactionAndLoyalty_PagesView.png)  

The performance is shown on video:
[Video](https://www.awesomescreenshot.com/video/42052588?key=41fbf4e04cc637eb33b4e349a3529ae5)

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

The dataset (orgin - .csv)   

includes customer records with attributes such as:

- Customer Segment (Group A / B)  
- Demographics (Gender, Age Group, Region)  
- Satisfaction ratings  
- Loyalty rating 
- Purchase history

  ![Dataset](https://github.com/bartoszsmielowski/PowerBI_CustomerSatisfactionAndLoyalty_DataDNA_JulyCallenge/blob/main/003%20Multimedia/Dataset_View.png)

---

## 🧼 Data Preparation (Power Query)

✔️ **Cleaning Steps**:
- Removed duplicates  
- Standardized categorical fields   

🔧 **Shaping & Modeling**:
- Built dimension tables such as: `Dim_Satisfaction`, `Dim_Customer`, `Dim_Location`, `Dim_Loyalty`  
- Created fact table: `Fact_CustomerSatisfaction`  
- Merged demographic data for unified analysis

  ![Tables](https://github.com/bartoszsmielowski/PowerBI_CustomerSatisfactionAndLoyalty_DataDNA_JulyCallenge/blob/main/003%20Multimedia/Tables_PowerQuery.png)

---

## 🧩 Data Model (Power BI)

Implemented a star schema for clarity and performance.  

![StarSchema](https://github.com/bartoszsmielowski/PowerBI_CustomerSatisfactionAndLoyalty_DataDNA_JulyCallenge/blob/main/003%20Multimedia/StarSchema.png)

🔗 **Key Measures**:
- `% HighLoyalty`  
- `AvgSatisfaction`  
- `Factor_Correlation`  

📐 **Model Highlights**:
- Clear relationships between dimensions and fact  
- Modular structure for scalable insights

---

## 📊 Report Pages — Analytical Breakdown

This report consists of **four analytical pages**, each designed to guide the user from high-level understanding to strategic action.  
Below is a breakdown of each page, including its purpose, visual design, and key insights.

---

### 🟦 Page 1 — Customer Pulse

  ![CustomerPulse](https://github.com/bartoszsmielowski/PowerBI_CustomerSatisfactionAndLoyalty_DataDNA_JulyCallenge/blob/main/003%20Multimedia/CustomerPulse_PageView.png)

**Purpose**:  
Provides a high-level snapshot of customer satisfaction and loyalty across segments and regions.

**Visualizations Used**:  
- KPI cards (e.g. % High Loyalty, Avg Satisfaction)  
- Combo chart (% High Lovalty vs Avg Satisfaction per Factor Group) 
- Region map (Loyalty distribution)

**Why These Visuals**:  
They offer immediate orientation — showing where loyalty is strongest, which groups dominate, and how satisfaction varies geographically.

**Key Insight**:  
Certain regions show loyalty gaps despite high satisfaction — prompting further investigation.

---

### 🟦 Page 2 — Group & Support  

![GroupSupport](https://github.com/bartoszsmielowski/PowerBI_CustomerSatisfactionAndLoyalty_DataDNA_JulyCallenge/blob/main/003%20Multimedia/GroupSupport_PageView.png)

**Purpose**:  
Compares segments across support-related factors and demographic dimensions.

**Visualizations Used**:  
- Clustered bar chart (Support Availability, Ease of Contact)  
- Demographic breakdowns (Gender, Age Group) by Clustered bar chart, Scatter chart and Donuts charts

**Why These Visuals**:  
They allow side-by-side comparison of satisfaction across segments, revealing behavioral and experiential differences.

**Key Insight**:  
Males are more loyal then Females. The 30-39 Age Group is the most loyal.

---

### 🟦 Page 3 — Factor Drivers  



**Purpose**:  
Evaluates which satisfaction factors statistically influence customer loyalty.

**Visualizations Used**:  
- Matrix table (Factors vs Loyalty %, Avg Satisfaction, Correlation)
- Column chart (Factor correlation)
- Map chart (Location Breakdown - Avg Satisfaction, % High Loyalty, Correlation)
- Dynamic narrative comments per factor

**Analytical Innovation**:  
A custom **correlation measure** was created to assess the strength of relationship between satisfaction and loyalty:  

`Factor_Correlation =  
VAR X = [AvgSatisfaction]  
VAR Y = [% HighLoyalty]  
RETURN  
CORREL(X, Y)`  

**Why This Matters?**  
Raw satisfaction scores can be misleading — correlation reveals which factors truly drive retention. This approach distinguishes popular features from strategic loyalty drivers, enabling smarter prioritization.

**Key Insight**: Factors like Brand Reputation and Support Availability show strong correlation with loyalty, while others (e.g. Price Perception) may be overvalued.  

---  
  
### 🟦 Page 4 — Strategic Recommendations  

**Purpose**:
Synthesizes correlation and retention data to highlight strategic gaps and opportunities.

**Visualizations Used**:
- Scatter chart (Correlation vs High Loyalty %)
- Narrative textbox with dynamic commentary
- Icon-based recommendation panel

**Why These Visuals**: 
The scatter chart visualizes tension between potential impact and actual performance — ideal for identifying underleveraged factors.

**Key Insight**: 
For example, Brand Reputation shows strong correlation but low retention — indicating a strategic gap. This page transforms data into decisions, guiding where to invest for maximum loyalty impact.
  
---


