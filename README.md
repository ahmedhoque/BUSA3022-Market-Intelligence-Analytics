BUSA3022 – Market Intelligence Analytics System

Project Overview

This repository contains the implementation plan and technical portfolio for the BUSA3022 Analytics Lead Case Study at Macquarie University.

The project centres on a fictitious post-trade analytics unit at Really Big Bank (RBB) and aims at creating a practical method for gathering, processing and presenting financial market data in order to assist with the analysis of market trends and for benchmarking future performance.

The solution looks at two Australian financial indicators: the RBA Interbank Overnight Cash Rate and the S&P/ASX 200 index.

Data Sources

1. Reserve Bank of Australia (RBA)

* Dataset: Interest Rates and Yields – Money Market – Daily (F1)
* Indicator: Interbank Overnight Cash Rate (%)
* Format: Excel (.xlsx)
* Source: https://www.rba.gov.au/statistics/tables/

2. Yahoo Finance

* Dataset: S&P/ASX 200 (^AXJO)
* Indicator: Daily closing index value
* Format: Retrieved using the Python yfinance library
* Source: https://finance.yahoo.com/quote/^AXJO/history/

The proof of concept at the beginning of the experiment spans the period from 16 June to 13 October 2026 and includes about 120 calendar days.

Part 1 – Data Pipeline Implementation

Objective

Demonstrate that financial data can be retrieved on a repeatable basis, stored separately from transformation processes, and checked for errors and missing observations.

Implemented Proof of Concept

The Python notebook demonstrates:

* Repeatable retrieval of RBA data using requests.
* Retrieval of S&P/ASX 200 market data using yfinance.
* Preservation of downloaded source data.
* Identification and logging of missing cash-rate observations.
* Detection and logging of failed HTTP requests.

Observed Results

During the October 2026 testing session:

* The RBA dataset contained 86 date records, including one missing cash-rate observation on 13 October 2026.
* The ASX 200 dataset contained 86 observations with no missing closing prices.
* A deliberately invalid RBA URL generated an HTTP 404 error, which was recorded in a CSV log.

These results describe the saved testing snapshot. Source values and missing observations may change following subsequent data publication or revision.

Proposed Production Architecture

The wider implementation would include scheduled ingestion, separate raw and curated storage, validation, transformation, metric calculation and management reporting.

Automated scheduling is proposed but has not been deployed in the current Google Colab proof of concept.

Repository Contents

* notebooks/ – Python notebook containing the Part 1 proof of concept.
* raw/ – Saved RBA and ASX 200 source-data snapshots.
* logs/ – Data-quality and simulated download-failure logs.
* diagrams/ – Proposed pipeline architecture in PNG and editable Draw.io formats.
* requirements.txt – Python libraries used by the project.

How to Run the Proof of Concept

1. Download the Part 1 Jupyter Notebook from the notebooks folder.
2. Open Google Colab at https://colab.research.google.com/.
3. Upload the notebook.
4. Run the dependency-installation cell.
5. Run the ingestion and data-validation cells in sequence.
6. Review the generated files in the raw and logs folders.
7. Run the deliberately invalid-URL test separately to demonstrate error handling.

Internet access is required to retrieve current source files. The saved snapshots and logs provide evidence of the original testing session.

AI Use and Validation

AI assistance was used during development of the Python workflow. Generated instructions and code were reviewed through execution and output checks.

One incomplete testing instruction was identified when changing a URL variable alone produced no output. The procedure was corrected by running the full HTTP request and exception-handling code, which successfully recorded a simulated 404 error.

Project Status

* Part 1 - Data Pipeline: Initial proof of concept and architecture completed.
* Part 2 - Data Curation: To be added.
* Part 3 - Dashboard and Reporting: To be added.

The repository will be updated as subsequent components are developed.

Academic Context

BUSA3022 - Managing Analytics and Algorithmic Systems
Macquarie University

This repository is an academic proof of concept, not a production banking platform.
