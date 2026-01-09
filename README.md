# Customer Segmentation for Microfinance Institutions in Cameroon Using Clustering

## Project Overview

This project focuses on customer segmentation for microfinance institutions in Cameroon using advanced clustering techniques. By analyzing transactional and demographic data, the project identifies distinct customer segments to enable personalized financial services, improve customer satisfaction, and optimize resource allocation. The approach leverages unsupervised machine learning algorithms (K-Means and Hierarchical Clustering) to uncover hidden patterns and insights for strategic decision-making in the microfinance sector.

The project encompasses the entire data pipeline: from data collection and preparation, through ETL (Extract, Transform, Load) processes, to OLAP (Online Analytical Processing) operations, and finally to clustering analysis and visualization. It utilizes a star schema data warehouse architecture implemented in PostgreSQL to facilitate efficient querying and analysis.

## Features

- **Data Warehouse Design**: Star schema with dimension and fact tables for efficient data storage and querying
- **ETL Pipeline**: Comprehensive data extraction, transformation, and loading processes
- **OLAP Operations**: Roll-up, drill-down, slicing, dicing, pivoting, trend analysis, and what-if analysis
- **Clustering Analysis**: K-Means and Hierarchical clustering for customer segmentation
- **Multiple Segmentation Approaches**:
  - Behavioral Segmentation (based on transaction patterns)
  - Value-Based Segmentation (based on financial value)
  - Geographic Segmentation (based on regional demographics)
- **Interactive Visualizations**: Scatter plots and cluster visualizations using Matplotlib
- **PostgreSQL Integration**: Robust database connectivity for data warehousing
- **Jupyter Notebook Interface**: Comprehensive analysis and visualization in an interactive environment

## Prerequisites

- **Python 3.8+**
- **Jupyter Notebook**
- **Conda (Anaconda or Miniconda3)** for environment management
- **PostgreSQL** (for data warehouse)
- **PgAdmin4** (recommended for database management)
- Required libraries are listed in `environment.yml`

## Installation and Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd DataWarehouse_project
```

### 2. Set Up the Environment

#### Using Conda (Recommended)

```bash
# Create environment from environment.yml
conda env create -f environment.yml

# Activate the environment
conda activate customer_segmentation_env
```

#### Alternative: Using pip

```bash
pip install -r requirements.txt
```

### 3. Set Up PostgreSQL Database

1. Install PostgreSQL and PgAdmin4
2. Create a new database named `Microfinance_DW`
3. Update database credentials in the notebook:

   ```python
   HOST = "localhost"
   DATABASE = "Microfinance_DW"
   USER = "your_username"
   PASSWORD = "your_password"
   PORT = "5432"
   ```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `Customer Segmentation.ipynb` and run the cells sequentially.

## Usage

1. **Data Loading**: The notebook loads data from CSV files in the `Data_Sets/` directory
2. **ETL Process**: Execute cells to perform data cleaning, transformation, and loading into PostgreSQL
3. **OLAP Operations**: Run analytical queries for roll-up, drill-down, slicing, dicing, etc.
4. **Clustering Analysis**: Perform K-Means clustering with elbow method for optimal cluster selection
5. **Visualization**: Generate scatter plots and cluster visualizations
6. **Insights Generation**: Analyze cluster characteristics for business recommendations

## Data Description

The project uses a star schema data warehouse with the following tables:

### Dimension Tables

- **Dim_Customer**: Customer demographics (User_id, Name, Age, Gender, Region, Preferred_language)
- **Dim_Branch**: Branch information (Branch_id, Branch_name, Region, Branch_manager)
- **Dim_Employee**: Employee details (Employee_id, Name, Region, Position)
- **Dim_Product**: Financial products (Product_id, Product_name, Product_type, Interest_rate)
- **Dim_Region**: Geographic regions (Region_id, Region_name, Population)
- **Dim_Loan_Application**: Loan applications (Application_id, User_id, Region, Loan_amount, Status)
- **Dim_Governance_Topic**: Governance topics (Topic_id, Topic_name, Mentions)
- **Dim_Account**: Account information (Account_id, User_id, Account_type, Balance)

### Fact Table

- **Fact_Transaction**: Transaction data (Transaction_id, User_id, Region, Transaction_date, Amount, Transaction_type, Currency)

## Methodology

### 1. Data Collection and Preparation

- Load data from CSV files
- Perform exploratory data analysis (EDA)
- Handle missing values, duplicates, and outliers

### 2. Data Warehouse Design

- Implement star schema architecture
- Create tables in PostgreSQL with appropriate relationships and constraints

### 3. ETL Process

- **Extract**: Read data from source CSV files
- **Transform**: Clean, normalize, and prepare data for analysis
- **Load**: Insert transformed data into the data warehouse

### 4. OLAP Operations

- **Roll-Up**: Aggregate data to higher levels (e.g., total revenue by region)
- **Drill-Down**: Examine detailed data at lower levels
- **Slicing and Dicing**: Filter and analyze data from multiple perspectives
- **Pivot**: Reorganize data for different views
- **Trend Analysis**: Identify patterns over time
- **What-if Analysis**: Simulate hypothetical scenarios

### 5. Clustering Analysis

- **Preprocessing**: Encode categorical variables, normalize features
- **Optimal Cluster Selection**: Use Elbow Method for K-Means
- **Clustering Algorithms**:
  - K-Means Clustering
  - Hierarchical Clustering (optional)
- **Segmentation Types**:
  - Behavioral Segmentation
  - Value-Based Segmentation
  - Geographic Segmentation

### 6. Visualization and Interpretation

- Generate scatter plots for cluster visualization
- Analyze centroids and cluster characteristics
- Derive business insights from segmentation results

## Results and Insights

### Clustering Results

- **Optimal Clusters**: 4 clusters identified using the Elbow Method
- **Behavioral Segmentation**: Customers grouped by transaction frequency and amount
- **Value-Based Segmentation**: Customers categorized by financial value and account balance
- **Geographic Segmentation**: Regional analysis based on population and transaction volume

### Key Findings

- Identification of high-value customers for targeted retention strategies
- Recognition of low-engagement segments for re-engagement campaigns
- Geographic insights for regional marketing and branch optimization
- Transaction pattern analysis for personalized product recommendations

### Business Recommendations

- Implement loyalty programs for high-value clusters
- Develop targeted marketing campaigns for different segments
- Optimize resource allocation based on regional performance
- Personalize financial products based on customer behavior patterns

## Project Structure

```
DataWarehouse_project/
│
├── Customer Segmentation.ipynb    # Main analysis notebook
├── environment.yml                # Conda environment configuration
├── README.md                      # Project documentation
├── .gitignore                     # Git ignore rules
│
└── Data_Sets/                     # Dataset directory
    ├── Dim_Branch.csv
    ├── Dim_Customer.csv
    ├── Dim_Employee.csv
    ├── Dim_Governance_Topic.csv
    ├── Dim_Loan_Application.csv
    ├── Dim_Product.csv
    ├── Dim_Region.csv
    ├── Fact_Transaction.csv
    └── Final_Dim_Account.csv
```

## Technologies Used

- **Programming Language**: Python 3.8+
- **Data Processing**: Pandas, NumPy
- **Machine Learning**: Scikit-learn
- **Visualization**: Matplotlib, Seaborn
- **Database**: PostgreSQL, SQLAlchemy
- **Environment Management**: Conda
- **IDE**: Jupyter Notebook

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments

- Data sourced from microfinance institutions in Cameroon
- Inspired by real-world applications of data warehousing and customer analytics
- Built as part of a comprehensive data science and analytics project
