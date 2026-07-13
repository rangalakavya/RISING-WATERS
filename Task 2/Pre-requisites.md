## Task 2: Technology Stack & Environment Configuration

The development environment has been initialized locally using an isolated Python virtual environment (`.venv`). The following core data science and web architecture libraries have been installed to drive the **Rising Water** predictive engine:

### Core Libraries Used
*   **Data Processing:** `NumPy` for numerical vector operations and `Pandas` for managing weather and rainfall data frames.
*   **Machine Learning:** `Scikit-learn` to build, train, and test classification/regression models for flood probability estimation.
*   **Data Visualization:** `Matplotlib` and `Seaborn` to construct correlation matrices, feature distributions, and seasonal rainfall plots.
*   **Web Framework:** `Flask` to establish our local WSGI development server, hosting the API endpoints that connect our ML models to the frontend interface.

### Project Dependencies Tracking
All active development dependencies and their precise version states have been frozen into the root configuration file:
*   `requirements.txt` — Maps the active runtime environment layout.

### Replication Guide
To recreate this identical workspace environment locally on your machine, run the following configuration sequence in your terminal:
```bash
# Activate your local virtual environment
.venv\Scripts\activate

# Install all locked package architectures
pip install -r requirements.txt
