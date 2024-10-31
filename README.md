## GITHUB API scrapping project report for Mumbai:50
umang bansal | 23f1002940 | 31-10-2024

* **Data Scraping**: Used a GitHub token and implemented a 1-second delay between requests to avoid exceeding API rate limits. Processed data through custom functions and stored the results in CSV format for further analysis.
* **Interesting Finding**: Analysis showed that developers marked as "hireable" maintain, on average, 54.05% more public repositories than non-hireable developers, suggesting that public repos play a role in personal branding for hireability. Additionally, a positive trend was observed where developers with higher public repo counts tend to be more hireable, potentially due to a stronger portfolio appeal.
* **Developer Recommendation**: To maximize performance, developers should avoid high-traffic hours on GitHub (6:00 am to 6:00 pm) for uploading large files, as activity is generally lower outside these hours. Moreover, new accounts created in January tend to gain more followers on average, so starting fresh at the beginning of the year could offer a visibility advantage.

### Data Scraping Explanation

1. **GitHub Token Creation:** Created a GitHub Token to surpass the standard API rate limits, allowing for a larger number of requests.
2. **Request Throttling:** Added a 1-second delay between requests to avoid exceeding the API limit.
3. **Function Definitions for Data Processing:** Defined various functions to import, clean, and process the data: `get_users_in_mumbai`, `clean_company_name`, `get_user_details`, and `get_user_repositories`.
4. **Data Storage:** Stored all processed data in CSV files.
5. **Post-Import Data Cleaning:** After importing, the data required further cleaning as specified in the project document. Used Pandas to convert Boolean values to strings (`true`/`false`) and replaced all `NaN`/`null` values with empty strings.
6. **GitHub Repository Upload:** Uploaded the CSV files to my GitHub repository.

### Interesting Findings

- **Correlation Insights:** The correlation heatmap of all numeric features showed that the correlation between the number of public repositories and the number of followers was 0.035, while the correlation between public repositories and the number of followings was 0.300.  
  - **Hypothesis:** This discrepancy could suggest that some developers create public repositories to build a personal portfolio, which could be beneficial for job applications.
  - **Hireability Histogram:** To explore this further, I plotted a histogram of the number of repositories grouped by hireability. The results indicated that as the number of repositories increases, the ratio of hireable individuals also increases.
  - **Outlier Analysis:** To ensure the findings weren't skewed by outliers, I calculated the mean number of repositories for hireable and non-hireable individuals before and after outlier removal (using IQR).
    - **Results:** On average, hireable individuals have 54.05% more public repositories than non-hireable individuals, increasing to 23.71% more after removing outliers.

### Actionable Recommendations

1. **Optimal Upload Times:** Most repositories (78.23%) are posted between 6:00 am and 6:00 pm, indicating peak activity during these hours. For developers uploading large files or resource-intensive content, consider doing so outside of these hours (after 6:00 pm or before 6:00 am).
2. **Account Creation Timing:** A histogram of average followers by account creation month revealed that accounts created in January have the highest average followers. With the new year approaching, starting a new account in January could be beneficial if aiming for a high follower count.
