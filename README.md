# 🎓 Scaler Learner Profiling via Clustering Case Study

## 🏢 About Scaler
**Scaler** is an online tech-versity that upskills software professionals and fresh graduates through industry-focused, live learning programs. This case study explores clustering techniques to segment learners by job roles, experience, and compensation using Scaler's anonymized internal database.

## 🎯 Objective

To identify meaningful learner segments using both **manual clustering** and **unsupervised machine learning** (K-Means, Hierarchical Clustering), enabling better insights into:
- Compensation trends across roles and companies
- Marketable skill sets
- High-growth clusters and salary benchmarking

## 📁 Dataset Overview
📥 Dataset: [scaler_clustering.csv](https://github.com/AkanshaSaini761/Scaler_Clustering_Case_Study/blob/main/scaler_clustering.csv)

| Column Name         | Description |
|---------------------|-------------|
| `email_hash`        | Anonymized learner identifier |
| `company_hash`      | Anonymized employer/company name |
| `orgyear`           | Year the learner started working |
| `ctc`               | Current CTC in INR |
| `job_position`      | Job profile (e.g., Backend Engineer, Data Scientist) |
| `ctc_updated_year`  | Year when CTC was last updated |

> 📌 Additional columns like `years_of_experience`, `designation_flag`, `class_flag`, `tier_flag` were created through feature engineering and clustering steps.

## 🔧 Key Analysis Steps

- Regex cleaning of job/company fields
- Missing value & outlier treatment
- Calculated `years_of_experience` from `orgyear`
- Performed **manual clustering** to generate:
  - `designation_flag` (Company + Role + Experience level)
  - `class_flag` (Company + Role)
  - `tier_flag` (Company level only)

- 5-point summaries of CTC for each flag category
- Top/bottom 10 earners by class and tier
- Label encoding and standardization for clustering
- Clustering:
  - Clustering tendency check using Hopkins statistic
  - **K-Means** (Optimal clusters = 3 via Elbow method)
  - **Hierarchical Clustering** for validation

## 📊 Insights

- **High Salary Disparity:** Wide range of CTC, with a median near ₹9.5L and extreme outliers (20 Cr) indicate inconsistencies.
- **Backend Engineers dominate** learner profiles.
- **Monopolistic Employer Trends:** One company (`xzaxvmhrro`) employs 8337 individuals.
- **Salary Growth Trend:** 50% of salary updates occurred post-2020, suggesting rapid industry adjustment.
- **Invalid Data Flags:** Incorrect values in `orgyear` and extreme CTC values require data cleaning.
- **Class-based CTC Variation:** Class 1 employees earn significantly more than Class 3, showing skill premium.
- **Tier-based CTC Variation:** Tier 1 companies offer higher compensation packages.
- **Clusters Identified:** 3 distinct learner groups based on experience & compensation.
  - Cluster 2: Highly experienced learners (8–24 yrs), high CTC.
  - Cluster 1: Moderate experience with balanced pay.
  - Cluster 0: Early-stage professionals, lower CTC.
- **Manual Cluster Flags:**
  - **designation_flag:** Salary vs peers in same company-role-exp
  - **class_flag:** Salary vs peers in same company-role
  - **tier_flag:** Salary vs peers in same company


## ✅ Recommendations

### 🔐 Data Quality
- **Implement Validation Rules**: Add strict checks on numeric and date inputs.
- **Clean Outliers**: Remove or flag CTC entries exceeding realistic ranges.

### 💼 Career & Curriculum Strategy
- **Target Roles**: Backend, Fullstack, QA, and Data Scientist roles show strong salary progression.
- **Focus on Skill Development**: Encourage learners to invest in foundational skills early.
- **Role-Specific Coaching**: Use clustering to personalize curriculum based on target job role and tier.

### 🧑‍🎓 Learner Support
- **Salary Benchmarking**: Offer CTC comparison tools by role and company tier.
- **Company Guidance**: Recommend companies like `xzaxvmhrro`, `axoy ztnfgqp` for high potential CTC.
- **Networking**: Enable mentorship or alumni connects for peer learning and referrals.
- **Internships**: Promote internship opportunities for salary growth leverage and job market entry.

## 🧰 Tools Used

- **Python**: pandas, numpy, seaborn, matplotlib
- **Clustering**: `KMeans`, `AgglomerativeClustering`, `Hopkins`, `Elbow Method`
- **Preprocessing**: `StandardScaler`, `LabelEncoder`
- **Regex**: `re.sub()` for string cleaning

## 📂 Output Report

📎 [Scaler_case_study_akansha_saini.pdf](https://github.com/AkanshaSaini761/Scaler_Clustering_Case_Study/blob/main/Scaler_case_study_akansha_saini.pdf)  
Includes exploratory analysis, clustering visuals, feature engineering logic, and key cluster-based segmentation outputs.

