# Supermarket Product Origins

**Discover where your food comes from. Make more informed, local purchasing decisions.**

Supermarket Product Origins is a Python-based data collection and analysis project designed to investigate the geographical origin of fresh food products sold by major Spanish supermarket chains.

By collecting product information from supermarket APIs and search endpoints, the project aims to make product provenance more transparent, help consumers identify locally sourced alternatives, and encourage more informed purchasing decisions that support local producers.

## Project Overview

The project currently integrates three Spanish supermarket chains:

- **Mercadona**
- **Carrefour**
- **ALDI**

It collects product information across several food categories, including fruit, vegetables, meat, fish, legumes, and dairy products, depending on the supermarket.

The collected data is processed and presented through an interactive Streamlit dashboard, allowing users to explore product information, inspect origin classifications, compare basic statistics, and export results for further analysis.

## Key Features

- **Multi-supermarket data collection:** Retrieve product information from multiple Spanish supermarket platforms.
- **Product categorization:** Organize products into food categories to facilitate exploration and analysis.
- **Origin analysis:** Examine product metadata, descriptions, and available origin information to identify potential geographical provenance.
- **Interactive dashboard:** Explore extracted products and summary statistics through a Streamlit interface.
- **Data export:** Download collected datasets in CSV format for further processing, visualization, or analysis.
- **Fallback data handling:** Use previously saved Carrefour results when live extraction fails and a local backup is available.
- **Data-driven sustainability:** Lay the groundwork for understanding product provenance and encouraging local food consumption.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data processing and tabular analysis |
| Requests | HTTP requests and API data collection |
| curl_cffi | HTTP requests with browser impersonation for Carrefour |
| Streamlit | Interactive web application and dashboard |
| Regular Expressions | Text processing and extraction of potential origin information |

## How It Works

The application follows a simple data collection and analysis workflow:

1. **Select a supermarket.** Choose Mercadona, Carrefour, or ALDI from the dashboard.
2. **Collect product data.** Query the corresponding product categories using the available endpoints.
3. **Process product metadata.** Extract information such as product names, categories, brands or suppliers, prices, and units.
4. **Analyze potential origins.** Examine available structured fields and textual clues to classify product provenance where possible.
5. **Explore the results.** View the collected products and summary statistics in the interactive dashboard.
6. **Export the dataset.** Download the results as a CSV file for additional analysis.

## Project Structure

```text
ProyectoSupermercado/
├── app.py
├── requirements.txt
├── scraper_mercadona.py
├── scraper_carrefour.py
├── scraper_aldi.py
├── analisis_carrefour.csv
└── README.md
```

*The structure above represents the main files used by the current application. Additional configuration and dependency files can be added as the project evolves.*

## Getting Started

### Requirements

- Python 3.10 or later
- Internet access
- Access to the required supermarket endpoints

### Installation

Clone the repository:

```bash
git clone https://github.com/andrew0v/ProyectoSupermercado.git
cd ProyectoSupermercado
```

Create and activate a virtual environment:

```bash
python -m venv .venv
```

On Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the dependencies:

```bash
pip install streamlit pandas requests curl_cffi
```

### Run the Application

Start the Streamlit dashboard:

```bash
streamlit run app.py
```

Open the local URL displayed in the terminal, select a supermarket, and click **Run Full Analysis** to begin collecting product data.

## Data and Origin Classification

A central objective of this project is to investigate the geographical provenance of food products. However, the availability and reliability of origin information vary across products and supermarket platforms.

The current implementation uses available product fields and text-based heuristics to estimate or identify potential origins. Consequently, a detected country should not automatically be interpreted as verified agricultural provenance.

In particular, a product's brand nationality, barcode prefix, manufacturing location, packaging location, and agricultural origin are distinct concepts.

The project therefore treats origin analysis as an ongoing data-quality challenge. More reliable provenance assessment requires explicit origin fields, traceable evidence, and clear distinctions between verified information, inferred classifications, and unknown origins.

## Current Limitations

- Product availability and endpoint behavior may change over time.
- Some supermarket endpoints may restrict automated requests or require session-specific parameters.
- Origin information may be missing, ambiguous, or inconsistent across sources.
- Text-based origin detection can produce false positives and requires further validation.
- Product prices and availability may depend on the selected store or delivery area.
- Fallback datasets may not reflect current products or prices.

## Future Improvements

Potential development directions include:

- Improving origin classification through validated product metadata.
- Separating country of origin, production region, processing location, and fishing area.
- Standardizing product identifiers and categories across supermarkets.
- Adding data-quality metrics and provenance confidence indicators.
- Expanding the analysis to more supermarket chains and product categories.
- Introducing geographical analysis to identify products originating near a user-defined location.
- Tracking data collection dates and changes in product information over time.
- Adding automated tests, structured logging, and more robust error handling.

## Academic Context

This project was developed as part of the **Data Science and Artificial Intelligence degree (CDIA)** at the **Universidad Politécnica de Madrid (UPM)**, in connection with the ALN course, during the 2026 academic year.

**Authors:** Alejandro Sánchez and Andrew Villamar.

## Disclaimer

This project is intended for educational and research purposes. It is not affiliated with, endorsed by, or officially associated with Mercadona, Carrefour, or ALDI. Data availability and access depend on the respective platforms and their applicable terms of use.

Product origin classifications should be treated as indicative unless supported by verifiable source information.
