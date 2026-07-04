# Bank-Note-Authentication
End-to-end currency forensics pipeline combining an optimized Random Forest classifier with an interactive Power BI dashboard to detect counterfeit banknotes with geometric precision.

# Banknote Authentication & Risk Analysis Dashboard

An end-to-end data analytics and machine learning project designed to identify counterfeit banknotes using physical geometric dimensions. This project combines a **Random Forest Classifier** predictive pipeline with an interactive **Power BI Dashboard** for proactive risk analysis and structural pattern discovery.

## Project Overview
Counterfeit currency poses an ongoing threat to financial operations. This project establishes a data-driven approach to:
1. **Predict:** Automatically classify whether a banknote is genuine or counterfeit based on structural measurements.
2. **Analyze:** Drill down into geometric risk factors (e.g., margins, length, diagonal dimensions) that correlate most heavily with fraudulent anomalies.

---

## Repository Structure
*   `fake_bills.csv` - Raw dataset containing physical measurements of 1,500 banknotes.
*   `Clean_Treasury_Bills.csv` - Cleaned dataset with class-specific dynamic median imputation, optimized for BI reporting.
*   `bank_note_authen_with_randomforest_classifier.ipynb` - Jupyter Notebook containing data exploration, preprocessing, and the Random Forest training workflow.
*   `Bank Note Visualization.pbix` - Power BI Desktop file containing the interactive risk analysis dashboard.

---

## Data Pipeline & Preprocessing
The raw dataset contains **37 missing values** strictly localized within the `margin_low` feature column. To preserve statistical integrity and distinct structural profiles:
*   **Dynamic Class Imputation:** Missing values were filled using the **median of their respective authenticity class** (Genuine vs. Counterfeit) rather than a naive global average.
*   **Label Mapping:** The target variable `is_genuine` (True/False) was refactored into descriptive categories (`Genuine` / `Counterfeit`) to streamline reporting schemas within Power BI.

### Banknote Features Included:
*   `diagonal` (mm)
*   `height_left` & `height_right` (mm)
*   `margin_up` & `margin_low` (mm)
*   `length` (mm)

---

## Predictive Modeling
The machine learning pipeline utilizes a **Random Forest Classifier** implemented via `scikit-learn` to handle non-linear decision boundaries among physical dimensions. 

*   **Libraries Used:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
*   **Validation Strategy:** Train-Test Split validation to ensure generalized performance against out-of-sample data points.

## Project Previews

### Python Exploratory Data Analysis
Below are the data distribution, feature interaction, and correlation visualizations generated during the initial exploration phase within the Jupyter Notebook:

```markdown
<!-- Python Preview Gallery -->
<p align="center">
  <img src="PythonPreview1.png" width="32%" alt="Feature Distribution Histograms" />
  <img src="PythonPreview2.png" width="32%" alt="Pairplot Class Separation" />
  <img src="PythonPreview3.png" width="32%" alt="Feature Correlation Matrix" />
</p>

## Power BI Interactive Dashboard
The companion dashboard transforms static model data into an operational risk scoping interface. 
<!-- Power BI Dashboard Gallery -->
<p align="center">
  <img src="Preview1_3.png" width="48%" alt="Dashboard Overview Layout" />
  <img src="Preview2_3.png" width="48%" alt="Dynamic Length Parameter Slicing" />
</p>
<p align="center">
  <img src="Preview3_3.png" width="48%" alt="Margin Low Risk Deep-Dive" />
  <img src="Preview4_3.png" width="48%" alt="Volume Threshold Breakdown" />
</p>

### Key Analytics Features:
*   **High-Level KPIs:** Instant visibility into **Total Scanned Volume** and the **Counterfeit Rate (%)**.
*   **Dynamic Feature Slicing:** Interactive parameter toggles allowing investigators to switch between different physical attributes (`length`, `margin_up`, `diagonal`, etc.) on the fly.
*   **Volume & Risk Distributions:** Dual-axis charts highlighting where high-density scan zones overlap with elevated counterfeit detection spikes.


