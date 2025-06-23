# Programming Languages in Transition: Trends, Correlations, and Future Outlook

### Course:
Big Data Engineering, FH Technikum Wien, Summer Semester 2025

### Team Members:
- Manpreet Misson  
- Timothy Gregorian  
- Omar Sidi Mammar

---

## Project Description

This project investigates the evolution, current usage, and future relevance of programming languages by analyzing long-term trends, short-term momentum, and salary correlations.  
The analysis combines data from multiple sources to explore whether a language's popularity aligns with its economic value — and which technologies are likely to grow or decline.

---

## Data Sources

- **GitHub Trending**  
  Daily scraped data from the GitHub Trending page (short-term signals)

- **GitHub REST API**  
  Repository metadata from 2007 to 2024 including language usage (long-term signals)

- **Stack Overflow Developer Surveys**  
  Annual survey data from 2015 to 2024 including salaries, language usage, countries, and experience levels

---

## Modules and Workflow

### 1. GitHub Trending (Short-Term)
- Daily scrape of GitHub’s trending page using BeautifulSoup
- Aggregation and cleaning of language data across multiple scrape days
- Filtering and normalization based on a defined whitelist
- Export as cleaned JSON dataset for streaming simulation

### 2. GitHub REST API (Long-Term)
- Yearly API queries for top-starred repositories (2007–2024)
- Extraction of language usage via secondary API calls
- Language normalization and blacklist filtering
- Final output as structured JSON for Spark-based long-term trend analysis

### 3. Stack Overflow Survey Data Cleaning
- Parsing of raw CSV survey files from 2015–2024 with year-specific logic
- Filtering for full-time developers and valid responses
- Standardization of salary, experience, language, and country fields
- Normalization of languages and countries using mapping dictionaries
- Export as cleaned yearly CSVs

### 4. Trend and Correlation Analysis
- GitHub API data used to analyze language usage over time (repository count and byte volume)
- Stack Overflow data used to:
  - Track popularity by developer count
  - Compare average salaries by language
  - Analyze experience and regional effects

### 5. Correlation Metrics
- Pearson and Spearman correlation computed between:
  - Language popularity (developer count)
  - Average salary (per language)
- Trends evaluated per year (2015–2024)

### 6. Composite Future Score
- Each language–experience–country combination is scored based on:
  - Normalized average salary
  - Developer popularity
  - Trend score from GitHub growth
  - Regional and experience-based salary averages
- A combined score helps identify high-potential technology profiles

---

## Inclusion Criteria for Programming Languages

Languages are only included if they satisfy:

- **Control Flow**: Must support `if`, `while`, `function`, etc.
- **General-purpose**: Must be suitable for building software, not only configuration or markup
- **Turing completeness**: Must be algorithmically expressive

Examples:

- **Included**: Python, JavaScript, Java, Rust, Go, C++
- **Excluded**: HTML, CSS, SQL, JSON

---

## Key Questions

- How has the popularity of programming languages changed between 2007 and 2025?
- Is there a measurable correlation between a language’s popularity and its average salary?
- Which programming languages and developer profiles show the strongest long-term potential?

---

## Technologies Used

- Apache Spark (batch processing, structured streaming)
- Apache Kafka (stream simulation)
- MinIO (S3-compatible object storage)
- Python (Pandas, Matplotlib, BeautifulSoup, Requests)
- Jupyter Notebooks
- GitHub REST API
- Stack Overflow survey CSVs

---

## Output Summary

- Cleaned daily trending dataset for Kafka streaming
- Long-term GitHub repository metadata (2007–2024)
- Cleaned and standardized Stack Overflow survey data (2015–2024)
- Final correlation plots, bar/area charts, and experience/salary trendlines
- Exported `trend_score` and `future_score` datasets

---

## Final Objective

This project provides a comprehensive perspective on programming languages:  
Not only which ones are popular, but also which ones are economically promising — and for whom.

--- 

## Data Access

The datasets used in this project are **not included in this GitHub repository** due to file size limitations.

###  Access the Data

You can access all required data files at the following location:

[http://172.29.16.105:9001/browser/bdenggroup4](http://172.29.16.105:9001/browser/bdenggroup4)

###  Folder Structure on the Data Server

- `CleanedCsvData/` – Preprocessed and cleaned CSV files  
- `RawCsvData/` – Raw source datasets  
- `RestAPIData/` – Data retrieved via REST API requests  
- `ScrapedData/` – Web scraping output  


