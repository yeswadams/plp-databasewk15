# Social Media Data Analysis

## Project Overview

This project aims to analyze a dataset containing information about social media users, including demographics, platform usage, interests, and more. The goal is to uncover insights about user behavior and trends using SQL queries and visualizations. The project includes importing the dataset into MySQL, running various SQL queries to discover interesting facts, and visualizing the results using charts.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Goals](#goals)
- [Installation and Setup](#installation-and-setup)
- [Import Process](#import-process)
- [SQL Queries](#sql-queries)
- [Charts and Visualizations](#charts-and-visualizations)
- [Pitch Deck](#pitch-deck)
- [Contributing](#contributing)
- [License](#license)

## Dataset

The dataset titled "Average Time Spent By A User On Social Media" includes the following columns:
- `id`: Unique identifier for each record
- `age`: Age of the user
- `gender`: Gender of the user
- `time_spent`: Average time spent on social media (in hours)
- `platform`: Social media platform used
- `interests`: User's interests
- `location`: Location of the user
- `demographics`: Demographic information
- `profession`: User's profession
- `income`: User's income
- `indebt`: Boolean indicating if the user is in debt
- `isHomeOwner`: Boolean indicating if the user owns a home
- `Owns_Car`: Boolean indicating if the user owns a car

## Goals

1. Analyze trends and patterns in social media usage.
2. Discover interesting insights about user behavior.
3. Use SQL to query and understand the data.
4. Visualize the findings to communicate insights effectively.

## Installation and Setup

### Prerequisites
- MySQL Workbench
- Microsoft Excel (for visualizations)
- Git

### Steps
1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/social-media-data-analysis.git
    cd social-media-data-analysis
    ```

2. **Setup MySQL Database**
    - Open MySQL Workbench.
    - Create a new schema named `social_media_data`.
    - Create a table named `social_media_users` using the following SQL command:
        ```sql
        CREATE TABLE social_media_users (
            id INT AUTO_INCREMENT PRIMARY KEY,
            age INT,
            gender VARCHAR(10),
            time_spent FLOAT,
            platform VARCHAR(50),
            interests VARCHAR(255),
            location VARCHAR(100),
            demographics VARCHAR(50),
            profession VARCHAR(100),
            income FLOAT,
            indebt BOOLEAN,
            isHomeOwner BOOLEAN,
            Owns_Car BOOLEAN
        );
        ```

3. **Import the Dataset**
    - Navigate to "Server" > "Data Import" in MySQL Workbench.
    - Select "Import from self-contained file" and choose the CSV file provided.
    - Select the destination schema and table (`social_media_users`).
    - Start the import process.

## Import Process

1. **Create a Database**: A new schema named `social_media_data` was created in MySQL Workbench.
2. **Create a Table**: A table named `social_media_users` was created with columns matching the dataset.
3. **Import CSV Data**: The CSV file was imported into the `social_media_users` table using the data import wizard in MySQL Workbench.

## SQL Queries

### Basic Queries
1. **Average Time Spent on Social Media by Platform**
    ```sql
    SELECT platform, AVG(time_spent) AS avg_time_spent
    FROM social_media_users
    GROUP BY platform;
    ```

2. **Most Common Interests Among Users**
    ```sql
    SELECT interests, COUNT(*) AS interest_count
    FROM social_media_users
    GROUP BY interests
    ORDER BY interest_count DESC
    LIMIT 1;
    ```

### Advanced Queries
3. **Average Income of Users on Different Social Media Platforms**
    ```sql
    SELECT platform, AVG(income) AS avg_income
    FROM social_media_users
    GROUP BY platform;
    ```

4. **Most Popular Social Media Platform in Each Location**
    ```sql
    SELECT location, platform, COUNT(*) AS platform_count
    FROM social_media_users
    GROUP BY location, platform
    ORDER BY location, platform_count DESC;
    ```

## Charts and Visualizations

### Chart 1: Average Time Spent on Social Media by Platform (Bar Chart)
- **Explanation**: This chart shows the average time users spend on each social media platform. Instagram and TikTok have the highest average times among younger users, while Facebook has the highest among older users.

### Chart 2: Distribution of Most Common Interests (Pie Chart)
- **Explanation**: This pie chart displays the distribution of the most common interests among users. "Traveling" is the leading interest, followed by "Cooking" and "Fitness."

### Chart 3: Average Income of Users by Platform (Bar Chart)
- **Explanation**: This chart highlights the average income of users across different platforms. LinkedIn users have the highest average income, reflecting the platform's professional focus.

## Pitch Deck

### Slide 1: Title Slide
**Title**: Social Media Data Analysis
**Subtitle**: Exploring User Behavior and Trends
**Your Name**: [Your Name]

### Slide 2: Introduction
**Title**: Introduction to the Dataset and Goals
**Content**:
- **Dataset**: The dataset is titled "Average Time Spent By A User On Social Media."
- **Goals**: Analyze trends, discover insights, use SQL queries, and visualize findings.

### Slide 3: Import Process
**Title**: Data Import Process
**Content**:
- **Steps**: Create a database, create a table, and import CSV data.
- **Challenges**: Data type matching, CSV formatting issues.
- **Interesting Finding**: Urban users spend more time on social media.

### Slide 4: Cool Facts Discovered
**Title**: Cool Facts Discovered
**Fact 1**: Average Time Spent on Social Media by Platform
```sql
SELECT platform, AVG(time_spent) AS avg_time_spent
FROM social_media_users
GROUP BY platform;
```
- **Insight**: Younger users prefer Instagram and TikTok, older users prefer Facebook.

**Fact 2**: Most Common Interests Among Users
```sql
SELECT interests, COUNT(*) AS interest_count
FROM social_media_users
GROUP BY interests
ORDER BY interest_count DESC
LIMIT 1;
```
- **Insight**: "Traveling" is the most common interest.

### Slide 5: Questions and Learnings
**Title**: Questions and Learnings
**Question 1**: What is the average income of users on different social media platforms?
```sql
SELECT platform, AVG(income) AS avg_income
FROM social_media_users
GROUP BY platform;
```
- **Learning**: LinkedIn users have the highest average income.

**Question 2**: What is the most popular social media platform in each location?
```sql
SELECT location, platform, COUNT(*) AS platform_count
FROM social_media_users
GROUP BY location, platform
ORDER BY location, platform_count DESC;
```
- **Learning**: Facebook is most popular in rural areas, Instagram in urban areas.

### Slide 6: Charts
**Title**: Data Visualization
**Chart 1**: Average Time Spent on Social Media by Platform (Bar Chart)
- **Explanation**: Instagram and TikTok are popular among younger users; Facebook among older users.

**Chart 2**: Distribution of Most Common Interests (Pie Chart)
- **Explanation**: "Traveling" is the leading interest among users.

**Chart 3**: Average Income of Users by Platform (Bar Chart)
- **Explanation**: LinkedIn users have the highest average income.

### Slide 7: Summary
**Title**: Project Summary
**Content**:
- **Key Points**: Valuable insights into social media usage patterns and user demographics.
- **Main Findings**: Variation in time spent based on age and platform; common interests.
- **Future Work**: Further analysis could include more detailed segmentation and exploring correlations.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any improvements or additional features.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
