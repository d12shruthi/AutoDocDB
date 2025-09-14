# AutoDocDB Dataset

This repository contains the dataset used to train and evaluate the AutoDocDB framework, as presented in the paper *"AutoDocDB: A Novel Framework for Automated Source Code Summarization in Database Management
Systems via Advanced Text Extraction and CodeT5+ Integration"*.

## Dataset Description

The dataset consists of **12,437 code snippets** extracted from DBMS source code, each containing embedded SQL queries. Each sample is paired with a high-quality, human-authored natural language summary.

### Sources
The code snippets were systematically collected from:
1.  **Textbooks**:
    -   Connolly and Begg, "Database Systems: A Practical Approach to Design, Implementation, and Management" (6th ed.)
    -   Ramakrishnan and Gehrke, "Database Management Systems" (3rd ed.)
    -   Garcia-Molina et al., "Database Systems: The Complete Book" (2nd ed.)
2.  **Official Documentation & Tutorials**: PostgreSQL, MySQL, SQLite, CockroachDB.
3.  **GitHub Repositories**: Repositories with 100+ stars, active maintenance, and professional patterns.

### Summary Creation
Summaries were authored by senior database developers (>5 years experience) following strict guidelines. They were validated through a rigorous three-phase process achieving high inter-annotator agreement (Cohen's κ = 0.87).

## Dataset Format (`dataset.json`)

The main dataset file is in JSON format, containing a list of objects. Each object has the following structure:

```json
{
  "id": "unique_string_identifier",
  "source": "textbook | official_docs | github",
  "source_name": "Connolly_Begg_6e | postgresql.org | owner/repo_name",
  "programming_language": "Java",
  "dbms": "PostgreSQL",
  "code": "full_code_string",
  "summary": "human_authored_summary_string",
  "operation_category": "Basic_CRUD",
  "complexity": "Low | Medium | High"
}
