# Financial House - Data Analyst Technical Test

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.5.3-brightgreen)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![n8n](https://img.shields.io/badge/n8n-workflow-purple)

This repository contains the complete deliverables for the Data Analyst technical test at **Financial House S.A**. The goal of this test is to demonstrate analytical rigor, data manipulation skills, and the ability to generate actionable business insights.

**Author:** Darlin Kuajo
**Date:** February 22-23, 2026

---

## Business Understanding

The test is structured in multiple parts, each simulating a real-world task a Data Analyst at Financial House might encounter:

1.  **Logic & Business Knowledge:** Assessing fundamental analytical thinking and understanding of the data analytics landscape.
2.  **Case Study 1 (Credit Repayment):** A high-level exercise on process, KPIs, and digital solutions for a business problem.
3.  **Case Study 2 (n8n Workflow):** A hands-on automation project to design a lead management system using n8n and AI, showcasing the ability to build efficient, low-code pipelines.
4.  **Case Study 3 (Transaction Analysis):** An in-depth exploratory data analysis (EDA) of 2,000 anonymized bank transactions to understand customer behavior, channel usage, and identify key patterns. (Files: `bank_transactions_cameroon_...csv`)
5.  **Case Study 4 (Credit Risk Analysis):** A comprehensive analysis of 500 clients to profile financial health, assess credit risk factors, and identify the most valuable and risky customer segments. (File: `bank_clients_cameroon_risk_...csv`)

The primary objective is not just to provide answers, but to **show the work**: the logical process, the code, the interpretations, and the final recommendations.

---

## Repository Structure

The repository is organized for clarity and ease of review.

financial-house-data-analyst-test/
│
├── README.md # This file: Project overview and structure
│
├── partie_4_n8n_workflow/ # Case Study 2: Lead Management Automation
│ ├── documentation.md # Conceptual design, technical choices, setup guide
│ └── lead_manager_workflow.json # The n8n workflow export file
│
├── partie_5_transactions/ # Case Study 3: Transaction Analysis
│ └── analyse_transactions.ipynb # Jupyter Notebook with full Python analysis
│
├── partie_6_credit_risk/ # Case Study 4: Credit Risk Analysis
│ └── analyse_credit_risk.ipynb # Jupyter Notebook with full Python analysis
│
└── rapport_final_darlin_kuajo.pdf # The final summary report for submission

---

## Technologies Used

- **Core Language:** Python 3.9
- **Data Manipulation:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook
- **Automation:** n8n (low-code workflow tool)
- **Version Control:** Git & GitHub

---

## How to Run the Analyses

The Python analyses are contained in Jupyter Notebooks (`.ipynb`).

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/darlinkua/financial-house-data-analyst-test.git
    cd financial-house-data-analyst-test
    ```

2.  **Set up a Python environment (recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**

    ```bash
    pip install pandas numpy matplotlib seaborn jupyter
    ```

4.  **Launch Jupyter and open a notebook:**
    ```bash
    jupyter notebook
    ```
    Navigate to `partie_5_transactions/` or `partie_6_credit_risk/` and open the `.ipynb` file.

All code is thoroughly commented to explain the logic behind each step.

---

## Approach & Methodology

The analyses in this project follow a structured, iterative process inspired by industry best practices (like CRISP-DM), as outlined in the provided reference document:

1.  **Ask the Question:** Each section of the notebooks starts by restating the business question to be answered.
2.  **Data Collection:** Loading the CSV data.
3.  **Data Preparation (Cleaning):**
    - Checking for missing values and duplicates.
    - Verifying and correcting data types (e.g., dates, numerical values).
    - Handling outliers where appropriate.
4.  **Exploratory Analysis:**
    - Generating descriptive statistics.
    - Creating calculated fields (e.g., client activity metrics, composite scores).
5.  **Interpretation & Visualization:**
    - Building clear, informative charts to illustrate findings.
    - Providing written insights and linking them back to the initial business questions.
6.  **Recommendations:**
    - Synthesizing the analysis into actionable business recommendations.

---

## Key Findings & Recommendations (Preview)

- **Transaction Analysis (Part 5):** Digital channels (Mobile & Online) dominate in volume, but ATMs are still crucial for high-value withdrawals in certain cities. Customer activity is multi-faceted; we identified distinct segments of "active" users based on frequency and volume.
- **Credit Risk Analysis (Part 6):** A clear correlation exists between a low credit score, a high number of loans, and default. We identified specific age groups and cities with higher risk profiles, as well as a segment of "high-potential" clients combining high income, high balance, and excellent credit scores.
- **n8n Workflow (Part 4):** A fully functional lead management system was designed, demonstrating the power of low-code automation to instantly qualify leads, provide AI-generated responses, and notify sales teams.

---

## Status

**Completed / Published** (as of February 23, 2026)

This repository represents the final deliverable for the technical test. The project is considered complete for this purpose.

---

## Credits

- **Candidate:** Darlin Kuajo
- **Evaluators:** Rodrigue Awomo, Arielle Wandji (Financial House S.A)
- **Data Source:** Provided by Financial House S.A for the purpose of this test.
