# Smart Meter MCP

Public API endpoint for smart meter data used in Kaggle GenAI Agent Capstone Project.

## API Endpoints

Access the smart meter CSV data via GitHub raw URLs:

### Standard Household
```
https://raw.githubusercontent.com/anandlonkar/smart-meter-mcp/main/sample_meter_data_2hr.csv
```
**Meter ID**: SM12345678901234  
**Pattern**: Typical household with peak usage in evenings (20:00-22:00)

### Night Shift Household
```
https://raw.githubusercontent.com/anandlonkar/smart-meter-mcp/main/night_shift_household.csv
```
**Meter ID**: SMNIGHT00000001  
**Pattern**: Minimal usage at night (00:00-08:00), high usage during afternoon/evening (12:00-20:00)  
**Characteristics**: House empty during night shift, active during day

### EV Charging Household
```
https://raw.githubusercontent.com/anandlonkar/smart-meter-mcp/main/ev_charging_household.csv
```
**Meter ID**: SMEVCAR00000001  
**Pattern**: Massive overnight charging spikes (00:00-06:00), normal daytime usage  
**Characteristics**: EV charging overnight (~10 kWh per 2-hour slot), typical Level 2 charger

### Preschool Kids Household
```
https://raw.githubusercontent.com/anandlonkar/smart-meter-mcp/main/preschool_kids_household.csv
```
**Meter ID**: SMKIDS100000001  
**Pattern**: High consistent usage throughout day (08:00-20:00), lower at night  
**Characteristics**: Kids and caretaker at home all day, constant activity

### Random/Unpredictable Household
```
https://raw.githubusercontent.com/anandlonkar/smart-meter-mcp/main/random_unpredictable_household.csv
```
**Meter ID**: SMRANDOM0000001  
**Pattern**: Erratic usage with strong seasonal variation (North Texas climate)  
**Characteristics**: 
- Summer (Jun-Sep): High AC usage, avg 2.85 kWh
- Winter (Dec-Feb): Moderate heating, avg 0.88 kWh
- Spring/Fall: Variable, avg 0.93 kWh

## Data Format

CSV format with the following columns:
- **ESIID**: Smart meter ID (identifies household type)
- **USAGE_DATE**: Date of usage (MM/DD/YYYY)
- **USAGE_START_TIME**: Start time of 2-hour interval
- **USAGE_END_TIME**: End time of 2-hour interval
- **USAGE_KWH**: Energy consumption in kilowatt-hours
- **ESTIMATED_ACTUAL**: A (Actual) or E (Estimated)
- **CONSUMPTION_SURPLUSGENERATION**: Type of reading

Data is aggregated to 2-hour intervals covering a full year (365 days, 4,380 records per household).

## Usage

This data is publicly available for demonstration purposes in the Power Plan Finder agent project. Each household type demonstrates distinct consumption patterns to test power plan recommendations.
