# SectionD_Group18_U.S.-Airbnb-Open-Data
# Multi-City Airbnb Host Strategy & Revenue Optimization Analysis

## EXECUTIVE SUMMARY

### Problem
The short-term rental market is highly competitive across major U.S. cities. Host performance varies significantly depending on pricing strategy, room type, occupancy management, and host professionalism. Understanding the drivers of revenue and occupancy is essential to optimize listing performance and improve overall platform profitability.

### Approach
A dataset of 10,000 listings across multiple cities was analyzed using Google Sheets. Key performance indicators (KPIs) such as Average Price, Occupancy Rate, Estimated Annual Revenue, Revenue per Available Day, and Host Performance Score were developed. Exploratory Data Analysis (EDA) was conducted to evaluate pricing trends, host segmentation, room type performance, city-level revenue distribution, and demand patterns. An interactive dashboard was created to support strategic decision-making.

### Key Insights
- Individual hosts show higher average occupancy as well as performance score and reviews as compared to professional hosts.
- Premium listings generate higher revenue but do not always achieve higher occupancy.
- Budget and average price categories maintain more stable occupancy rates.
- Revenue concentration is significantly higher in top metropolitan cities.
- Minimum night requirements influence listing demand distribution.
- All the room types have occupancy rates similar to each other, but the revenue through Entire Property listing is higher.

### Key Recommendations
- Optimize pricing bands based on occupancy elasticity and have a wider category pricing.
- Encourage professional host & commercial operators to improve pricing strategies and maintenance.
- Focus acquisition efforts on high-revenue metropolitan markets.
- Promote balanced minimum night policies to increase demand.
- Use performance-based host segmentation for strategic planning.

---

## SECTOR & BUSINESS CONTEXT

### Travel & Short-Term Rental Industry Overview
The short-term rental industry has experienced significant growth over the past decade, driven by the expansion of digital platforms such as Airbnb and increased demand for flexible, experience-driven travel. Major metropolitan cities including New York, Los Angeles, San Francisco, and Chicago dominate revenue generation due to high tourism and business travel demand.

The market is characterized by intense competition among hosts, price variability, and demand fluctuations influenced by seasonality, location, and listing type. As supply increases across cities, host performance optimization becomes critical for sustaining revenue growth.

### Business Challenges in the Industry
Despite strong market growth, several structural challenges exist:
- Revenue concentration in a small percentage of hosts
- Pricing inefficiencies across different market segments
- Variability in occupancy rates across host types
- Imbalance between premium pricing and demand stability
- Impact of minimum night requirements on booking behavior

Data-driven strategy is essential to identify performance drivers and optimize listing outcomes.

### Why This Problem Was Chosen
The dataset of 10,000 listings across multiple U.S. cities reveals substantial differences in:
- Host type performance
- Revenue distribution across cities
- Price category impact on occupancy
- Demand variation based on listing structure

Given the competitive nature of the travel and hospitality sector, understanding the relationship between price, occupancy rate, host segmentation, and estimated annual revenue is critical for strategic decision-making.

---

## PROBLEM STATEMENT & OBJECTIVES

### Problem Statement
The short-term rental market shows significant variation in revenue and occupancy across cities, pricing segments, and host types. Even within the same platform, listings generate different booking rates and annual revenues.

**Core problem addressed:**  
*How can revenue and occupancy be optimized by identifying high-performing hosts, effective pricing strategies, and demand patterns using data-driven analysis?*

### Project Scope
**Analysis focuses on:**
- 10,000 Airbnb listings across multiple U.S. cities
- Host segmentation (Individual, Professional, Small and Commercial Operator)
- Pricing categories (Budget, Average, Premium)
- Occupancy rate and estimated annual revenue
- Revenue distribution across cities
- Minimum nights and demand behavior

*External factors such as seasonality and competitor pricing are not included.*

### Project Objectives
- Compare host performance across segments
- Analyze the relationship between price and occupancy
- Identify high-revenue cities
- Evaluate demand based on minimum night policies
- Determine top revenue-generating hosts
- Optimise pricing strategies and booking types
- Generate actionable business insights

### Success Criteria
The project will be successful if:
- Clear KPIs are defined
- Revenue drivers are identified
- Insights are supported by visual analysis
- Strategic recommendations are data-backed
- The dashboard enables performance monitoring

---

## DATA DESCRIPTION

### Dataset Overview
The dataset contains 10,000 Airbnb listings across multiple U.S. cities. Each record represents an individual listing with details related to pricing, location, host type, availability, and performance metrics.

### Structure & Variables
**Key variables include:**
- **Price** – Nightly listing price
- **Calculated Host Listings** - No. of listings of a particular host
- **Number of reviews** - No. of customer reviews received for the listing
- **Availability 365** - No. of days the listing is available
- **Room Type** – Entire Home/Apt, Private Room, Shared Room, Hotel Room
- **City** – Listing location
- **Minimum Nights** – Required booking duration

### Derived Metrics
Additional performance indicators calculated:
- **Price Category** – Budget, Premium or Average
- **Occupancy Rate** – Rate of bookings
- **Host type** – Normalised category based on number of listings
- **Annual Revenue** – Yearly revenue generated
- **Demand & Performance Score** – Based on price, reviews, occupancy

### Limitations
- Revenue values are estimated
- No seasonal breakdown available
- No customer demographic data
- No cancellation or competitor pricing data
- No positive/negative review sentiment data

---

## DATA CLEANING & PREPARATION

### Data Preparation
- Original dataset received in **ARFF format**
- Converted to **CSV format** for analysis
- Randomly sampled from ~200,000 rows to **10,000 rows**
- Prepared in **Google Sheets** for EDA and dashboard
- Python processing: [Google Colab Link](https://colab.research.google.com/drive/1r1ycdqGrEKu3HduKjgcKH_Wjd_M6a87G?usp=sharing)

### Cleaning Process
- Standardized categorical fields (Host Type, Room Type, City)
- Converted neighbourhood zip codes to text format
- Removed duplicate and incomplete records
- Removed outliers using **IQR method**

### Missing Values Handling
| Field | Treatment |
|-------|-----------|
| **neighbourhood_group** | 5000+ missing → "Not Specified" category |
| **neighbourhood** | Mixed formats → All text; numerics → 0 |
| **minimum_nights** | ≤0 or >90 → Median replacement |

### Feature Engineering
- **Occupancy Rate**: `(365-availability_365)/365`
- **Annual Revenue**: `price*(365 - availability_365)`
- **Revenue per Available Day**: `price*occupancy_rate`
- **Price Category Segmentation**
- **Host Performance Score**
- **Host Type Segmentation**

---

## KPI & METRIC FRAMEWORK

| KPI | Definition | Formula | Why it Matters | Key Objectives |
|-----|------------|---------|----------------|---------------|
| **Total Revenue** | Total projected yearly revenue | `SUM(estimated_revenues)` | Core financial health | High-revenue cities, top hosts |
| **Avg Occupancy Rate** | % available days booked | `AVG(Occupancy Rate)` | Demand strength indicator | Price-occupancy analysis |
| **Average Price** | Avg nightly price | `AVG(Price)` | Pricing positioning | Pricing optimization |
| **RevPAD** | Revenue per available day | `Total Revenue ÷ Total Available Days` | Revenue efficiency | Host performance comparison |
| **Avg Minimum Nights** | Avg stay requirement | `AVG(Minimum Nights)` | Booking flexibility | Minimum night policies |
| **Total Listings** | Active listing count | `COUNT(Listing ID)` | Platform scale | Market analysis |

---

## EXPLORATORY DATA ANALYSIS

### Trend Analysis 
![Alt text]([https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA])
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
###Key Findings
- **Revenue concentration** in few high-performing cities
- **Entire homes** → Higher revenue (not always higher occupancy)
- **Private Rooms** → Higher/stable occupancy (customer loyalty)
- **Professional hosts** → Disproportionate revenue contribution
- **Individual hosts** → Better price-occupancy balance
- **High minimum nights** → Lower occupancy/revenue


### Comparison Analysis 
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
###Key Findings
- **Commercial operators**: High revenue/listing, low occupancy efficiency
- **Private rooms**: High occupancy, lower revenue/listing
- **High-revenue cities**: Pricing power (not highest occupancy)
- **Price elasticity**: Higher pricing ≠ higher revenue


### Distribution Analysis 
![Alt text]([image-path-or-url](https://drive.google.com/drive/folders/1GgH34Mo--KsOvxOD5Zc2f3j6MLlCfonA))
![Alt text](image-path-or-url)
![Alt text](image-path-or-url)
###Key Findings
- **Revenue**: Right-skewed (few listings dominate)
- **Price**: Mid-range clustering
- **Host distribution**: Most own 1 listing
- **Occupancy**: Moderate variance (demand stability)
- **Premium pricing**: High revenue, low demand


### Correlation Analysis 
![Alt text](image-path-or-url)
![Alt text](image-path-or-url)
![Alt text](image-path-or-url)
###Key Findings
- **Price vs Occupancy**: Weak inverse relationship
- **Minimum Nights vs Occupancy**: Negative correlation
- **Reviews vs Revenue**: Positive relationship
- **Listings per Host vs Revenue**: Higher total revenue

---

## ADVANCED ANALYSIS

### Revenue Concentration
Revenue heavily concentrated in **major metropolitan cities**. Small % of listings contribute disproportionately to total revenue.

### Host Performance Insights
**Individual hosts** → Higher occupancy vs professional segments (operational flexibility advantage).

### Pricing & Demand Dynamics
**Budget/mid-range** segments maintain stable demand. **Premium pricing** shows demand elasticity limits.

### Key Revenue Drivers
1. City-level demand
2. Pricing category
3. Host type
4. Minimum night policy
5. Listing availability

---

## DASHBOARD DESIGN

Interactive **Google Sheets dashboard** with pivot tables, formulas, and slicers.
![Alt text](image-path-or-url)


### Dashboard Components
| Section | Content |
|---------|---------|
| **KPI Summary** | Revenue, Listings, Occupancy, Pricing |
| **Analytical Charts** | City comparison, Price vs Occupancy, Host Segmentation |
| **Demand Insights** | Minimum Nights vs Listings |
| **Top Performers** | Revenue-generating hosts |


### Interactive Filters
- Neighbourhood
- Host Type
- Minimum Nights
- Price Categories
- Room Type

---

## INSIGHTS SUMMARY

### Key Strategic Findings
1. **Revenue Geography**: Major metro dominance
2. **Host Performance**: Individual > Professional (occupancy)
3. **Pricing Reality**: Professional hosts - good revenue, poor retention
4. **Policy Impact**: High minimum nights → Low occupancy/revenue
5. **Demand Stability**: Budget/mid-range pricing wins
6. **Pareto Principle**: Few listings drive most revenue

---

## STRATEGIC RECOMMENDATIONS

### 1. Optimize Pricing Strategy
Dynamic pricing in budget/mid-range segments
Avoid unsupported premium pricing

### 2. Geographic Focus

Prioritize top metro markets for expansion
Low-revenue areas need strong demand validation
### 3. Host Performance Improvement
Pricing guidance for professional hosts
Regular inspections (revenue/review-based)

text

### 4. Minimum Night Policies
Flexible requirements → Higher booking frequency

text

### 5. Dashboard Monitoring
Real-time KPI tracking for demand shifts

text

---

## IMPACT ESTIMATION

| Initiative | Revenue Impact | Occupancy Impact | Efficiency Impact |
|------------|---------------|------------------|-------------------|
| **Pricing Optimization** | High | Medium | High |
| **Metro Market Focus** | High | Low | Medium |
| **Host Performance** | Medium | High | High |
| **Minimum Nights** | Medium | High | Medium |
| **Dashboard Monitoring** | Medium | Medium | High |

---

## LIMITATIONS

### Data Constraints
- **Sample size**: 10,000/226,000 listings
- **Revenue**: Estimated (not actual transactions)
- **No seasonality**: Static annual view
- **External factors**: Regulations, competitors excluded

### Geographic Issues
- Neighborhood data inconsistent/missing

---

## FUTURE SCOPE

1. **Seasonal Analysis** – Time-series demand patterns
2. **Dynamic Pricing** – ML price optimization
3. **Review Analytics** – Sentiment/performance correlation
4. **Neighborhood Targeting** – Granular location insights
5. **Predictive Models** – High-revenue listing prediction

---

## CONCLUSION

**Analysis of 10,000 Airbnb listings** revealed:

✅ **Revenue concentration** in metro markets  
✅ **Individual host occupancy advantage**  
✅ **Pricing elasticity limits**  
✅ **Minimum nights demand impact**  

**Interactive dashboard** enables real-time monitoring and data-driven optimization for sustainable short-term rental growth.

---

## APPENDIX

### A. Dataset Summary

| Feature | Type | Distinct Values | Missing |
|---------|------|-----------------|---------|
| id | Numeric | 226,029 | 0 |
| host_id | Numeric | 130,425 | 0 |
| neighbourhood_group | String | 34 | 115,845 |
| neighbourhood | String | 1,450 | 0 |
| room_type | String | 4 | 0 |
| price | Numeric | 1,975 | 0 |
| minimum_nights | Numeric | 169 | 0 |
| reviews_per_month | Numeric | 1,242 | 48,602 |
| availability_365 | Numeric | 366 | 0 |
| city | String | 28 | 0 |

### B. Calculated Fields Reference

| Field | Formula |
|-------|---------|
| **occupancy_rate** | `(365-availability_365)/365` |
| **estimated_annual_revenue** | `price*(365-availability_365)` |
| **revenue_per_available_day** | `price*occupancy_rate` |
| **host_performance_score** | `(reviews/host_listings)*occupancy*reviews_per_month` |

### C. Team Contribution Matrix

| Team Member | Dataset Prep | KPI/Analysis | Dashboard | Report | PPT | Role |
|-------------|--------------|--------------|-----------|--------|-----|------|
| Yashi Agrawal | ARFF→CSV | KPI curation | Charts | Content | Creation | Lead Analyst |
| Archit Gosain | Design | - | Full design | Report | - | Dashboard Lead |
| Shivam Dixit | Sampling | Fields | Charts | Cleaning | - | Data Engineer |
| Prince Singh | Sampling | Fields | Charts | Cleaning | - | Data Engineer |
| Kavya Mukhija | Outliers | Slicers | Design | PPT | Cleaning | QA Lead |
| Samay Samrat | Cleaning | Charts | - | Cleaning | - | Data Cleaning |
| Pratyush Parida | Connections | - | Interactivity | - | - | Dashboard Dev |

### D. Processing Notes
Original: ~226K records (ARFF)

Analysis sample: 10K records (CSV)

Missing neighbourhood_group → "Not Specified"

minimum_nights capped: 1-90 range

Processed in Google Sheets

text

**Team Signatures:**  
Yashi Agrawal | Archit Gosain | Shivam Dixit | Prince Singh | Kavya Mukhija | Samay Samrat | Pratyush Parida

**Links:**  
📊 [Google Sheets Dashboard]([insert-link](https://docs.google.com/spreadsheets/d/1uUS19DZOmRPpP0dIIqeO2hyi-BboDQyT7nwTV-ibpg8/edit?usp=sharing))  
📄 [Full Report]([insert-link](https://www.canva.com/design/DAHBkrILuRY/18MnbsAozONtbbR1yO2ijg/edit?utm_content=DAHBkrILuRY&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton))  
🎯 [PPT Presentation]([insert-link](https://www.canva.com/design/DAHBnVQ7Or4/HI0f5QFrERjA3XLOAzoC8w/edit?utm_content=DAHBnVQ7Or4&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton))
