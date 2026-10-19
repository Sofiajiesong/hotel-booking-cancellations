# Hotel Booking Cancellations

## Team
Sofia Song and Alicia Osuna Fernandez  
MSBA 502 – Analytics Programming

## Project Goal
We study which hotel bookings are more likely to be canceled and how managers could use this information to prioritize guest follow-up.

## Files
- `502_Hotel_Booking_Data_Analysis.ipynb`: Python code, charts, and analysis results.
- `hotel_bookings.csv`: Original dataset.
- `README.md`: Project overview and instructions.

## Data Source
Hotel Booking Demand dataset by Antonio, Almeida, and Nunes (2019).

The original dataset contains 119,390 bookings and 32 variables from two hotels in Portugal, with arrival dates from 2015 to 2017.

Dataset link:
https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

## How to Run
1. Download the notebook and `hotel_bookings.csv`.
2. Open the notebook in Google Colab.
3. Click Run all.
4. Upload `hotel_bookings.csv` when prompted.
5. The notebook will produce the tables, charts, and model results.

Python libraries used: pandas, numpy, matplotlib, scipy, and scikit-learn.

## Analysis
- Missing-value checks and data cleaning.
- Cancellation patterns by hotel type, lead time, market segment, arrival month, room rate, and length of stay.
- Two-proportion z-test and chi-square test.
- Logistic regression with a 75% training and 25% testing split.
- Model evaluation and comparison of prediction thresholds.
- Arrival-year validation and cancellation risk tiers.

## Main Results
The current cleaning process leaves 86,611 bookings, with a cancellation rate of 27.69%.

City Hotel bookings have a cancellation rate of 30.21%, compared with 23.71% for Resort Hotel bookings. Cancellation rates also increase across the lead-time groups.

At a 0.50 prediction threshold, the model achieves:
- Accuracy: 74.3%
- Baseline accuracy: 72.3%
- Precision: 62.2%
- Recall: 18.5%
- ROC-AUC: 0.730

Lowering the threshold to 0.30 increases recall to 67.8%, but lowers precision to 44.4% and flags 42.3% of bookings.

## Business Recommendation
Hotels could use predicted risk to prioritize a small reconfirmation pilot. The pilot should measure whether follow-up improves outcomes before expanding the approach.

## Limitations
The data covers only two hotels from 2015–2017. Results show associations, not causes.

The notebook removes agent and company before deduplicating the remaining columns. This choice changes cancellation rates substantially, and similar records may represent separate bookings.

The dataset does not provide enough information to calculate actual vacancy rates. The analysis also does not prove that follow-up will reduce cancellations or increase revenue.
