# Flood Prediction System - Database Design

This document details the Entity Relationship Diagram (ERD) architecture for the database tracking system. It structures user data, weather metrics, and machine learning outputs.

## Core Entities & Attributes

1. **User Table**
   - `User_ID` (Primary Key) — Unique identifier for system operators.
   - `User_Name` — Full name of the user.
   - `Email` — Secure login address.
   - `Password` — Encrypted access string.
   - `Role` — Permissions profile (e.g., Admin, Meteorologist, Disaster Officer).

2. **Weather_Data Table**
   - `Data_ID` (Primary Key) — Unique ID for each submitted environmental record.
   - `User_ID` (Foreign Key) — Relates the entry back to the specific User who logged it.
   - `Annual_Rainfall` — Recorded total yearly precipitation.
   - `Seasonal_Rainfall` — Tracked precipitation during high-risk seasons.
   - `Temperature` — Average ambient temperature reading.
   - `Humidity` — Relative air moisture percentage.
   - `Cloud_Visibility` — Measured atmospheric clarity metrics.

3. **ML_Model Table**
   - `Model_ID` (Primary Key) — Unique identifier for the deployment model.
   - `Model_Name` — Identifier label for the specific version tracker.
   - `Algorithm_Type` — The underlying ML logic used (e.g., Random Forest, Linear Regression).
   - `Accuracy` — Validated performance score of the model.
   - `Model_File` — Filepath tracking where the trained weights are saved.

4. **Prediction Table**
   - `Prediction_ID` (Primary Key) — Unique log index for the calculation output.
   - `Data_ID` (Foreign Key) — Links back to the exact weather metrics analyzed.
   - `Model_ID` (Foreign Key) — Identifies which specific model version generated the result.
   - `Prediction_Result` — Final output categorization (e.g., Flood / No Flood).
   - `Flood_Probability` — Explicit percentage chance calculated by the engine.
   - `Prediction_Date` — Timestamp recording when the assessment took place.

## Relationships & Cardinality

- **User → Weather_Data (One-to-Many):** A single team member or automated operator can submit multiple weather reports over time.
- **Weather_Data → Prediction (One-to-One):** Every singular weather metric log yields exactly one dedicated prediction record.
- **ML_Model → Prediction (One-to-Many):** A single deployed machine learning model version is reused to evaluate many separate prediction queries.
