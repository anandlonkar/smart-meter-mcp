# Smart Meter MCP

Public API endpoint for smart meter data used in Kaggle GenAI Agent Capstone Project.

## API Endpoint

Access the smart meter CSV data via:
```
https://raw.githubusercontent.com/anandlonkar/smart-meter-mcp/main/sample_meter_data_2hr.csv
```

## Data Format

CSV format with the following columns:
- ESIID: Smart meter ID (anonymized as SM12345678901234)
- USAGE_DATE: Date of usage
- USAGE_START_TIME: Start time of interval
- USAGE_END_TIME: End time of interval
- USAGE_KWH: Energy consumption in kilowatt-hours
- ESTIMATED_ACTUAL: A (Actual) or E (Estimated)
- CONSUMPTION_SURPLUSGENERATION: Type of reading

Data is aggregated to 2-hour intervals covering November 2024 to March 2025.

## Usage

This data is publicly available for demonstration purposes in the Power Plan Finder agent project.
