# Fitness Center Analytics on SAP HANA Cloud

End-to-end analytics project built during an SAP HANA Cloud training program:
data model, calculation views, SQLScript, row-level security, REST API and dashboard.

![Dashboard](docs/dashboard.png)

## What it does
- Layered data model in HDI: tables → staging → intermediate → reporting views
- Calculation views: Star Join cube, restricted columns, input parameters,
  Union, Rank and Window Function (running total, moving average, month-over-month)
- Multi-currency conversion with date-valid exchange rates
- SQLScript table and scalar functions (trainer performance, commission)
- Row-level security: analytic privileges and roles
- Performance analysis: Explain Plan, join and union pruning
- Node.js/Express REST API (CRUD, parameterized queries) and Chart.js dashboard

## Tech stack
SAP HANA Cloud, SAP Business Application Studio, HDI, SQL/SQLScript,
Node.js, Express, @sap/hana-client, Chart.js, Git

## Architecture
[Short description or diagram: HANA views → Express API → dashboard]

## Key views
| View | Purpose |
|------|---------|
| CV_SALES_STAR_SCHEMA | Star join cube: bookings with dimensions |
| CV_BOOKINGS_WITH_ANALYTICS | Window functions: running total, MoM change |
| CV_CLASSES_MULTI_CURRENCY | Currency conversion with exchange rates |
| ... | ... |

## Run locally
1. Deploy the HDI container (`db/`) to your own SAP HANA Cloud instance
2. `cd srv && cp .env.example .env` and fill in your credentials
3. `npm install && npm start`
4. Open http://localhost:3000

## Security notes
No credentials are stored in the repo; configuration is read from environment variables.


