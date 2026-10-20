# Predicting Hotel Booking Cancellations

ADS-505 | Applied Data Science Program | University of San Diego | Team 7

## Project Objective

Identify booking characteristics associated with hotel cancellations and compare classification models to support targeted reservation follow-up. Evaluate the tradeoff between detecting cancellations and incorrectly flagging bookings that would be honored.

## Installation and Execution

1. Clone the repository:

   ```bash
   git clone https://github.com/relliott1/ADS-505-Hotel-Cancellations-Project.git
   cd ADS-505-Hotel-Cancellations-Project
   ```

2. Install the required packages:

   ```bash
   python -m pip install jupyter numpy pandas matplotlib seaborn scikit-learn
   ```

3. Download and extract `hotel_bookings.csv` from the [dataset page](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand). Place it in the same folder as the notebook.

4. Launch Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open the technical notebook (`.ipynb`) and select **Kernel → Restart Kernel and Run All Cells**.

Results appear in the notebook. Figures are also saved to `eda_figures/`. KNN tuning may take several minutes or longer.

## Contributors
| Ryan Elliott |
| Mitchell Capp |
| Selin Karadag |

## Methods and Technologies

**Methods:** Exploratory data analysis, data cleaning, feature engineering, classification, cross-validation, hyperparameter tuning, and threshold analysis.

**Technologies:** Python, Jupyter Notebook, pandas, NumPy, Matplotlib, seaborn, scikit-learn, Git, and GitHub.

## Project Description

The Hotel Booking Demand dataset contains 119,390 bookings and 32 variables from one city hotel and one resort hotel. Arrival dates span July 2015 through August 2017.

Predictors include lead time, stay length, guest counts, market segment, deposit type, room type, previous cancellations, and special requests. The target, `is_canceled`, identifies canceled bookings as 1 and non-canceled bookings as 0.

### Research Questions

- Which booking characteristics are associated with cancellation?
- How do cancellation patterns differ between hotel types?
- How do classification models compare?
- How do thresholds affect cancellation detection and follow-up workload?

### Modeling and Results

Preprocessing addresses missing values, duplicates, unusual records, and feature engineering. Reservation status fields are excluded because they reveal the outcome.

We compare logistic regression, K-nearest neighbors, decision tree, and random forest. KNN uses cross-validated hyperparameter tuning. Performance is assessed using precision, recall, F1, ROC-AUC, and confusion matrices.

The reported decision tree achieved precision of 0.667, recall of 0.528, F1 of 0.589, and ROC-AUC of 0.837 at a threshold of 0.5. It is the provisional preferred default-threshold configuration for cancellation screening. Random forest achieved the highest reported ROC-AUC of 0.859.

### Limitations and Next Steps

KNN uses a different split from the other models. Country grouping occurs before splitting, and model selection and threshold exploration use test outcomes. Final selection requires consistent partitions, training-only preprocessing, and validation-based model and threshold selection.

The data represent two hotels during 2015-2017. Future work should evaluate later booking periods, probability calibration, and whether targeted follow-up improves outcomes enough to justify its workload.

## Data Source

[Hotel Booking Demand dataset on Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)

**Source publication:**  
António, N., de Almeida, A., & Nunes, L. (2019). Hotel booking demand datasets. *Data in Brief, 22*, 41-49. https://doi.org/10.1016/j.dib.2018.11.126

## AI Disclosure

AI tools were used to assist with portions of the code and documentation. See the team’s AI interaction log for details.
