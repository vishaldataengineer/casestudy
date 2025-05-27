# GA4 ETL Pipeline Documentation

## **Project Overview**
- **Purpose**: Transform raw GA4 eCommerce data into business-ready metrics
- **Owner**: Analytics Team (@your-email)
- **Key Stakeholders**: Marketing, Sales, Product Management teams.
- **Data Source**: `bigquery-public-data.ga4_obfuscated_sample_ecommerce.events_*` (3 months of sample data)
- **Architecture**: Medallion (Bronze → Silver → Gold)


## **Data Flow**
```mermaid
graph LR
    A[Bronze: GA4 Events] --> B[Silver: Cleaned Purchases]
    B --> C[Gold: Traffic Source Metrics]
```

## **Key Tables**
| Layer | Table | Description |
|-------|-------|-------------|
| Bronze | `ga4_events` | Raw GA4 event data |
| Silver | `purchase_traffic_source` | Cleaned purchase events |
| Gold | `top_traffic_source` | Monthly performance by channel |

## **How to Run**
1. Compile: `dataform compile`
2. Execute: `dataform run --tags daily`
3. Test: `dataform test`

---
