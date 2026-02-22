# 📊 Data Professional Survey Breakdown - Power BI Project

A comprehensive Power BI dashboard analyzing survey responses from 630 data professionals worldwide, providing insights into salaries, job satisfaction, career transitions, and industry trends.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-4285F4?style=for-the-badge&logo=google-analytics&logoColor=white)

---

## 📊 Dashboard Preview

![Dashboard Preview](Screenshot-2026-02-22-120124.png)


---

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Dataset Information](#dataset-information)
- [Key Insights](#key-insights)
- [Dashboard Features](#dashboard-features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Data Cleaning & Transformation](#data-cleaning--transformation)
- [Visualizations](#visualizations)
- [Key Findings](#key-findings)
- [Future Enhancements](#future-enhancements)
- [Author](#author)

---

## 🎯 Project Overview

This Power BI project analyzes survey data from data professionals to uncover trends and patterns in:
- **Job roles and titles** in the data industry
- **Salary distributions** across different positions
- **Career transitions** into data fields
- **Programming language preferences**
- **Job satisfaction metrics** (salary, work-life balance, management, etc.)
- **Demographics** (age, gender, education, location)
- **Barriers to entry** in the data profession

**Purpose**: To provide actionable insights for aspiring data professionals, recruiters, and organizations looking to understand the current state of the data industry.

---

## 📊 Dataset Information

### Dataset Overview
- **Total Records**: 630 survey responses
- **Total Columns**: 28 attributes
- **Data Source**: Survey conducted among data professionals
- **File Format**: `.xlsx` (Excel)

### Key Attributes

| Category | Attributes |
|----------|------------|
| **Demographics** | Age, Gender, Country, Ethnicity, Education Level |
| **Professional Info** | Job Title, Industry, Salary, Career Switch Status |
| **Technical Skills** | Favorite Programming Language |
| **Job Satisfaction** | Salary, Work/Life Balance, Coworkers, Management, Upward Mobility, Learning Opportunities |
| **Career Journey** | Difficulty Breaking into Data, Job Search Priorities |

### Survey Questions Covered

1. **Q1**: Which Title Best Fits your Current Role?
2. **Q2**: Did you switch careers into Data?
3. **Q3**: Current Yearly Salary (in USD)
4. **Q4**: What Industry do you work in?
5. **Q5**: Favorite Programming Language
6. **Q6**: Job Satisfaction Metrics (6 aspects)
7. **Q7**: How difficult was it to break into Data?
8. **Q8**: Most important factor when looking for a new job
9. **Q9**: Gender
10. **Q10**: Current Age
11. **Q11**: Country of Residence
12. **Q12**: Highest Level of Education
13. **Q13**: Ethnicity

---

## 💡 Key Insights

### Job Roles Distribution
- **Data Analyst**: 381 respondents (60.5%)
- **Student/Looking/None**: 90 respondents (14.3%)
- **Data Engineer**: 38 respondents (6.0%)
- **Data Scientist**: 25 respondents (4.0%)
- **Others**: Various specialized roles

### Programming Languages
- **Python**: 420 respondents (66.7%) - Most Popular
- **R**: 101 respondents (16.0%)
- **SQL**: 41 respondents (6.5%)
- **Others**: JavaScript, C/C++, DAX, etc.

### Career Transitions
- **59%** switched careers into data
- **41%** started directly in data roles

### Education Background
- **Bachelor's Degree**: 329 (52.2%)
- **Master's Degree**: 192 (30.5%)
- **High School**: 36 (5.7%)
- **Associate's**: 16 (2.5%)
- **PhD**: 5 (0.8%)

### Demographics
- **Average Age**: 29.9 years
- **Age Range**: 18 - 92 years
- **Gender Split**: 74.3% Male, 25.7% Female

### Difficulty Breaking into Data
- **Neither easy nor difficult**: 42.7%
- **Difficult**: 24.8%
- **Easy**: 21.3%
- **Very Difficult**: 7.0%
- **Very Easy**: 4.3%

---

## 🎨 Dashboard Features

### Interactive Visualizations
- **Salary Analysis by Role**: Compare average salaries across different data positions
- **Programming Language Popularity**: Visual breakdown of preferred languages
- **Job Satisfaction Scores**: Multi-dimensional satisfaction metrics
- **Geographic Distribution**: Survey respondents by country
- **Career Transition Insights**: Career switch patterns and trends
- **Difficulty to Break In**: Barrier analysis for entering the field
- **Age and Experience Analysis**: Demographic trends

### Key Metrics Cards
- Total Survey Respondents
- Average Salary
- Average Age
- Career Switchers Percentage
- Most Popular Programming Language
- Average Satisfaction Score

### Filters and Slicers
- **Job Role**: Filter by specific positions
- **Country**: Geographic filtering
- **Education Level**: Filter by educational background
- **Career Switch**: Yes/No filter
- **Gender**: Male/Female filter
- **Age Range**: Age group filtering

---

## 🛠️ Technologies Used

- **Power BI Desktop**: Dashboard creation and visualization
- **Microsoft Excel**: Data source and initial analysis
- **Power Query**: Data cleaning and transformation
- **DAX (Data Analysis Expressions)**: Custom calculations and measures
- **Power BI Service**: Dashboard publishing and sharing (optional)

---

## 🚀 Getting Started

### Prerequisites
- **Power BI Desktop** (Download from [Microsoft Store](https://www.microsoft.com/en-us/download/details.aspx?id=58494))
- **Microsoft Excel** (for viewing the dataset)
- Windows 10/11 or compatible OS

### Installation Steps

1. **Clone or Download the Repository**
   ```bash
   git clone https://github.com/CODERGURU26/Data-Professional-Survey-PowerBI.git
   ```

2. **Open the Dataset**
   - Navigate to the project folder
   - Open `Power_BI__Project_-_Data_Professional_Survey_Breakdown_Dataset.xlsx` to explore the raw data

3. **Open Power BI File**
   - Double-click `Power_BI_Project_-_Data_Professional_Survey_Breakdown.pbix`
   - Power BI Desktop will launch with the dashboard

4. **Refresh Data** (if needed)
   - Click on "Refresh" in the Home tab to update visualizations

---

## 🧹 Data Cleaning & Transformation

### Power Query Steps

1. **Column Renaming**: Simplified long question names for better readability
2. **Data Type Conversion**: Ensured correct data types (text, number, date)
3. **Handling Missing Values**: Addressed null values in optional fields
4. **Salary Parsing**: Cleaned and standardized salary ranges into numerical values
5. **Programming Language Standardization**: Consolidated variations (SQL, sql, Sql)
6. **Age Outlier Handling**: Verified age range consistency
7. **Country Standardization**: Unified country name formats
8. **Custom Columns**: Created calculated columns for analysis

### DAX Measures Created

```dax
// Average Salary
Average Salary = AVERAGE('Survey Data'[Salary])

// Total Respondents
Total Respondents = COUNT('Survey Data'[Unique ID])

// Career Switchers %
Career Switch % = 
DIVIDE(
    CALCULATE(COUNT('Survey Data'[Unique ID]), 'Survey Data'[Career Switch] = "Yes"),
    COUNT('Survey Data'[Unique ID]),
    0
) * 100

// Average Satisfaction Score
Avg Satisfaction = 
AVERAGE('Survey Data'[Satisfaction Score])

// Median Age
Median Age = MEDIAN('Survey Data'[Age])
```

---

## 📈 Visualizations

### 1. **Salary by Job Title**
- **Chart Type**: Horizontal Bar Chart
- **Purpose**: Compare average salaries across different data roles
- **Insight**: Data Scientists and Data Engineers command higher salaries

### 2. **Programming Language Preference**
- **Chart Type**: Donut/Pie Chart or Tree Map
- **Purpose**: Show distribution of favorite programming languages
- **Insight**: Python dominates with 66.7% preference

### 3. **Job Satisfaction Matrix**
- **Chart Type**: Stacked Bar Chart or Gauge
- **Purpose**: Visualize satisfaction across 6 different aspects
- **Metrics**: Salary, Work-Life Balance, Coworkers, Management, Upward Mobility, Learning

### 4. **Career Transition Breakdown**
- **Chart Type**: Donut Chart
- **Purpose**: Show percentage of career switchers vs. direct entrants
- **Insight**: 59% switched careers into data

### 5. **Geographic Distribution**
- **Chart Type**: Map Visualization or Bar Chart
- **Purpose**: Show respondent distribution by country
- **Insight**: Identifies key markets for data professionals

### 6. **Difficulty to Break In**
- **Chart Type**: Column Chart or Funnel
- **Purpose**: Analyze perceived difficulty of entering the field
- **Insight**: Most find it "Neither easy nor difficult"

### 7. **Education Level Distribution**
- **Chart Type**: Column Chart
- **Purpose**: Show educational background of data professionals
- **Insight**: Bachelor's and Master's degrees are most common

### 8. **Age Distribution**
- **Chart Type**: Histogram or Box Plot
- **Purpose**: Analyze age demographics
- **Insight**: Average age is 29.9 years, indicating a young workforce

---

## 🔍 Key Findings

### 1. **Python is King**
Python is the overwhelmingly preferred programming language (66.7%), followed by R (16%). SQL variations account for 6.5%.

### 2. **Data Analyst is the Most Common Role**
Over 60% of respondents identify as Data Analysts, making it the entry point for most data professionals.

### 3. **Career Switching is Common**
59% of data professionals switched careers, indicating the field is accessible to career changers.

### 4. **Young Workforce**
The average age of 29.9 years suggests a young and dynamic workforce in the data industry.

### 5. **Gender Gap Exists**
74.3% male vs. 25.7% female respondents highlight an ongoing gender disparity in tech.

### 6. **Education Matters**
82.7% have at least a Bachelor's degree, with 30.5% holding Master's degrees.

### 7. **Mixed Difficulty Perception**
Breaking into data is perceived as moderately difficult by most (42.7%), with only 25.6% finding it easy.

---

## 🔮 Future Enhancements

- [ ] Add trend analysis with historical survey data
- [ ] Include salary prediction model based on role and experience
- [ ] Implement drill-through pages for detailed role analysis
- [ ] Add comparison filters for year-over-year changes
- [ ] Create mobile-optimized dashboard layout
- [ ] Include industry-specific salary breakdowns
- [ ] Add Q&A visual for natural language queries
- [ ] Implement tooltips with additional context
- [ ] Create automated PDF report generation
- [ ] Add bookmarks for different user personas

---

## 📝 How to Use This Project

### For Aspiring Data Professionals
- Understand salary expectations for different roles
- Identify the most in-demand programming languages
- Gauge the difficulty of breaking into the field
- Determine optimal educational paths

### For Recruiters & HR
- Benchmark salary offerings against industry standards
- Understand candidate preferences and priorities
- Identify skill gaps in the market
- Tailor job descriptions based on insights

### For Current Data Professionals
- Compare your situation with industry peers
- Identify areas for skill development
- Understand career advancement opportunities
- Make informed career decisions

### For Educators & Training Providers
- Align curriculum with industry demands
- Focus on popular programming languages
- Address barriers to entry
- Design targeted training programs

---

## 📂 Project Structure

```
Data-Professional-Survey-PowerBI/
│
├── Power_BI_Project_-_Data_Professional_Survey_Breakdown.pbix
│   └── Main Power BI dashboard file
│
├── Power_BI__Project_-_Data_Professional_Survey_Breakdown_Dataset.xlsx
│   └── Raw survey data (630 records, 28 columns)
│
├── README.md
│   └── Project documentation (this file)
│
└── assets/ (optional)
    └── Dashboard screenshots and images
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

### Author

**Gururaj Krishna Sharma**

- 📧 Email: [guruuu2468@gmail.com](mailto:guruuu2468@gmail.com)
- 💼 LinkedIn: [Gururaj Krishna Sharma](https://www.linkedin.com/in/gururaj-krishna-sharma)
- 💻 GitHub: [@CODERGURU26](https://github.com/CODERGURU26)

---

## 🌟 Acknowledgments

- Survey participants who shared their data
- Power BI community for inspiration and best practices
- Microsoft for Power BI Desktop and documentation
- Data professionals worldwide contributing to the field

---

## 🎓 Learning Outcomes

This project demonstrates proficiency in:
- ✅ Power BI dashboard design and development
- ✅ Data cleaning and transformation with Power Query
- ✅ DAX measures and calculated columns
- ✅ Interactive visualization creation
- ✅ Data storytelling and insight generation
- ✅ Survey data analysis
- ✅ Business intelligence reporting

---

**⭐ If you find this project helpful, please consider giving it a star!**

---

*Last Updated: February 2026*
