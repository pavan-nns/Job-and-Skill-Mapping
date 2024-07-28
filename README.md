# Job and Skill Mapping Dashboard

## Introduction

The project aims to create a user-friendly dashboard that maps various occupations in various industries across different demographic regions. The dashboard will help job seekers make informed career choices by evaluating data from O*NET and BLS OEWS resources. The visualizations will show the skills, technologies, and employment statistics required for various occupations, enabling users to consider potential career routes and training opportunities. This project seeks to narrow the gap between job seekers and employers by providing a platform to learn the necessary skills for success.

## Insight Needs

The primary stakeholders of this project are job seekers, career advisors, beginners, and students, who use this data to explore career options and plan their professional paths. This project is an important initiative that will have a positive impact on individuals and the job 
market as a whole. The project requires insights in the following areas:
- Clustering related occupations and skills using graph or network analysis.
- Analyzing temporal trends with employment and wage statistics.
- Distribution of occupation statistics.
- Comparing multiple occupations with respect to skills.
- Conducting geospatial analysis for job listings.
- Allowing users to filter and explore data by selecting their interested skills.

## Data Acquisition

O*NET is a comprehensive online repository managed by the U.S. Department of Labour that provides in-depth details about various occupations in the United States. The dataset contains tables related to occupations and skills, available in different file formats such as XLS, MySQL, Oracle, and Text. The BLS OEWS dataset contains employment and wage statistics and is available in national, state, metropolitan, and non-metropolitan categories from 1990 to 2021.

## Data Description

We are working with the skills and technology skills databases from the O*NET dataset. The skills dataset has 61,110 entries representing associations between 873 unique occupations and 35 unique skills measured using the Level and Importance scales. The technology skills dataset has 31,461 entries representing associations between 923 unique occupations and 8695 unique technology skills. Each occupation has an example technology skill classified as either hot or not and in demand or not.
<p align="center">
  <img src="https://github.com/user-attachments/assets/b93c9168-851b-4319-9273-161f07c57a52" />
</p>

The 2021 Occupational Employment and Wage Statistics dataset from the U.S. Bureau of Labour Statistics has 33 columns and 214,096 records, offering employment and salary statistics for various job positions in the United States. It provides a comprehensive view of employment trends and wages across states and areas.
<p align="center">
  <img src="https://github.com/user-attachments/assets/bd6d47e7-7cb0-4727-b1be-2e92200caed0" />
</p>

## Data Pre-processing

We created a skills and technology skills database from the O*NET website data, including only the necessary columns for analysis and visualizations. The skills table contains over 60,000 rows, and the technology skills table contains more than 30,000 rows. To make the resulting graphs meaningful and easy to interpret, we filtered the data according to scale reference, and relevance.
The skills table contains two entries for each occupation and skill, measuring the corresponding scale and indicating skill relevance. The "not_relevant" column in the original table had "N" and "Y" values for "Level" scale rows and null values for "Importance" scale rows. To ensure accurate filtering based on skill importance and relevance, we replicated the "not_relevant" value from "Level" to "Importance" scale rows for each unique occupation and skill entry. 
We customized the data to complement each visualization based on stakeholder needs and filtered it according to Scale - Level, Scale - Importance, and data_value. For the technology skills table, we filtered it to include only hot and in-demand technologies.
The Occupational Employment and Wage Statistics (OEWS) Survey was used to obtain data on employment and wage statistics for various occupations in the United States over five years. The data from 2021 to 2017 was merged in Excel and analyzed using pandas to determine employment trends in different industries and occupations.

## Data Analysis

In the data preprocessing stage, we employed multiple tools like SQL, Excel, and Python to clean and filter the data. We ensured that the data was structured appropriately before moving on to conducting an in-depth analysis to derive meaningful insights. The analytical techniques we utilized included temporal, geospatial, topical, network, and relational analysis. The temporal analysis helped us identify trends in the data over time. The geospatial analysis helped us find trends and patterns in different regions and locations. The topical analysis allowed us to identify the topics that emerged from the data, while network analysis helped us examine relationships and connections between various occupations and skills. Additionally, relational analysis enabled us to understand the relationships between different variables and how they interacted with each other.
To present the insights effectively, we used visualization tools such as Tableau, PowerBI, and Gephi. We created interactive and engaging visualizations that will help stakeholders understand the insights and trends better. The approach ensured that the data was thoroughly analyzed, and valuable insights were extracted and presented in an easily understandable format.

## Visualizations

We developed four distinct dashboard concepts, each tailored to address a specific problem statement, to meet the varying needs of the stakeholders. We did not rely on any pre-existing 
templates or visualizations for this project. Instead, we prioritized the stakeholders' requirements and carefully crafted an interactive and user-friendly dashboard that offers valuable insights. The approach involved a thorough analysis of the most critical issues, and the dashboards were designed to address those needs in the most effective way possible.

### 1. Histogram

We utilized Tableau to create a histogram visualization aimed at understanding the relevance and importance of skills across various occupations in the dataset. To achieve this, we filtered the data based on relevance and scale, specifically the Level where the data_value 
was greater than 3, indicating higher significance of that particular skill to the occupation. The resulting histogram plotted all the skills on the Y-axis and the count of occupations on the X-axis, allowing us to gain insights into the distribution of skills across the dataset.

<p align="center">
  <img src="https://github.com/user-attachments/assets/ad907754-a5e5-4d5b-a739-5b3970d6dd2e" />
</p>

### 2. Word Cloud

To create the visualization, we used the technology skills table from the O*NET dataset, where the primary attribute was the "Hot Technology" column. This column indicates whether a skill is a hot technology (Y) or not (N). We filtered the data to only show values where "Hot technology" was marked as "Y" and generated a word cloud using Tableau based on this filtered data. Overall, this approach allowed us to visualize the most in-demand technology skills and gain insights into the current job market's technology demands.

<p align="center">
  <img src="https://github.com/user-attachments/assets/922df402-dadf-4a1e-90ff-6cf28303af18" />
</p>

### 3. Stacked Bar Chart

We created a stacked bar chart in TableWe created a stacked bar chart in Tableau to visualize and compare the hot and in-demand skills required for the occupations in the dataset. The chart was created by filtering the dataset to only include the "Occupations" and "Hot and In-demand skills" columns. The hot and in-demand skills were filtered using the "Hot Technology" and "In-demand" columns, where both columns had a value of "Y".
Through this visualization, users can focus on a specific occupation and gain insights into the hot technologies associated with it. The filters also enable comparisons between two or more occupations in terms of their hot technologies. This approach allowed us to effectively communicate the most in-demand skills for each occupation and provided stakeholders with valuable insights into the current job market's technological demands.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c08f4066-c075-4557-b714-64d117dd918f" />
</p>

### 4. Geospatial Dashboard

Utilizing the OEWS employment data for 2021, we developed a geospatial visualization that presents employment statistics in an easy to understand format. The visualization enables users to apply filters based on specific occupations to learn about total employment figures in a given state. The more jobs, the darker the color in each state. 
Additionally, it provides information on the number of jobs available per 1000 people for the selected occupation, further enhancing users' understanding of employment trends.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a676ff31-bb7a-43e7-bf9a-803861974959" />
</p>

### 5. Box Plot

To create this box plot visualization, we utilized the OWES dataset and Tableau tool. The color hue on the plot represents the ownership type, and it compares the average annual mean of different sectors over five years to identify any changes over time. 
Using box plots in this visualization allowed us to graphically represent the distribution of data, providing insights into the central tendency and variability of wages across different ownership types.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d806b15d-b7a3-4031-8be5-97656fbd33da" />
</p>

## Interpretation of Results

- According to the histogram, critical thinking, reading comprehension, active listening, monitoring, and several other skills are highly demanded for a variety of occupations. On the other hand, some important skills such as installation, equipment selection, and technology design are only relevant to specific occupations.
- The word cloud reveals that Microsoft's bundle of software, including Microsoft Excel, Microsoft Word, and Microsoft Office, are essential technical skills required for all occupations. In contrast, other hot technical skills are unique to each occupation.
- Based on the stacked bar graph, software developers, web developers, database architects, and blockchain engineers require a significant number of hot technical skills. Additionally, Microsoft Office software is required for most occupations. However, there are certain occupations such as clergy, captains, mates, and pilots of water vessels that have specific hot technical skills.
- Based on the geospatial dashboard, the state with the highest number of jobs is CA, followed by TX, NY, and FL. However, when filtered specifically for data science jobs, WY, AR, and PR have no jobs available, while CA and NY have the most employment opportunities in this field.
- The box plot shows the dispersion of annual salaries (range: 45k-53k) across different sectors from 2017 to 2021. The Federal government sector had the highest mean salary (75k-85k) consistently, while the Private local government gambling sector had the lowest. All sectors, except Private and Postal Services, experienced consistent increases in mean salary. Notably, the Private and Postal Services sector witnessed a significant decrease in mean salary between 2020 and 2021.
