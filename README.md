# Hotel-bookings-Analysis-with-python
This project analyzes hotel booking data to uncover insights into customer behavior, booking patterns, and pricing strategies. The dataset contains information such as booking status, customer type, lead time, cancellation trends, seasonal demand, and revenue metrics.
# Hotel Booking Analysis

**Author:** Abhishek Kumar
**GitHub:** [https://github.com/Abhishekkumar903](https://github.com/Abhishekkumar903)

---

## Project Overview

This project analyzes hotel booking data to extract actionable insights about booking trends, customer behavior, cancellations, and pricing strategies. Using Python (Pandas, NumPy) and visualization libraries (Matplotlib, Seaborn), the analysis focuses on the Kaggle *Hotel Booking Demand* dataset to help hotel management make data-driven decisions.

## Dataset

Key columns used in the analysis include:

* `hotel`: Type of hotel (`City Hotel` / `Resort Hotel`)
* `is_canceled`: Booking cancellation status (0 = not canceled, 1 = canceled)
* `lead_time`: Days between booking and arrival
* `arrival_date`: Arrival date (year, month, day)
* `stays_in_weekend_nights`, `stays_in_week_nights`
* `adults`, `children`, `babies`
* `meal`: Meal plan
* `country`: Guest country
* `market_segment`, `distribution_channel`
* `is_repeated_guest`, `previous_cancellations`, `booking_changes`
* `deposit_type`, `agent`, `company`
* `days_in_waiting_list`, `customer_type`
* `adr`: Average Daily Rate (price per night)
* `required_car_parking_spaces`, `total_of_special_requests`
* `reservation_status`, `reservation_status_date`

**Source:** Kaggle — *Hotel Booking Demand*.

---

## Objectives

1. Analyze booking and cancellation trends.
2. Quantify the impact of `lead_time` on cancellations.
3. Explore seasonal (monthly/quarterly) booking patterns and ADR trends.
4. Compare performance between City Hotel and Resort Hotel.
5. Visualize metrics to support insights and recommendations.

---

## Tools & Libraries

* Python 3.x
* Pandas, NumPy
* Matplotlib, Seaborn
* Jupyter Notebook

---

## Installation & Setup

```bash
# Clone the repository
git clone <repository-url>
cd hotel-analysis

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # macOS / Linux
venv\Scripts\activate     # Windows

# Install required packages
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook
```

Open `hotel_analysis.ipynb` to run the analysis and view visualizations.

---

## Analysis Workflow

1. **Data loading & inspection** — read dataset, examine columns, basic stats.
2. **Data cleaning & preprocessing**

   * Handle missing values (e.g., `children`, `country`, `agent` if applicable).
   * Convert `arrival_date`/`reservation_status_date` to `datetime`.
   * Create consolidated date features: `arrival_date_month`, `arrival_year`, `arrival_month_num`, `weekday`, `season`.
   * Remove duplicates and invalid rows (e.g., negative ADR).
3. **Feature engineering**

   * `total_nights` = `stays_in_weekend_nights` + `stays_in_week_nights`
   * `total_guests` = `adults` + `children` + `babies`
   * `adr_per_person` = `adr` / `total_guests` (handle zero-guest cases)
4. **Exploratory data analysis (EDA)**

   * Booking volume over time (monthly/seasonal trends).
   * ADR trends across time and hotel types.
   * Cancellation rates by hotel type, market segment, deposit type, lead time bins.
   * Lead time distribution and its correlation with cancellations.
   * Guest geography and market segment breakdowns.
5. **Visualizations**

   * Time series plots (monthly bookings, ADR)
   * Bar charts (cancellations by type, top markets)
   * Heatmaps (bookings by month and day of week)
   * Boxplots (ADR distribution by hotel and season)

---

## Key Metrics & Example Findings

> The README below lists example findings — update these after running the notebook on the dataset.

* **Cancellation patterns:** City Hotels generally show higher cancellation rates than Resort Hotels.
* **Lead time:** Longer lead times correlate with higher cancellation probability; short lead times have lower cancellation rates.
* **ADR differences:** Resort Hotels typically have higher ADRs than City Hotels, with strong seasonality (summer peaks for resorts).
* **Seasonality:** Resorts peak in summer months; City Hotels remain more consistent throughout the year with business demand spikes on weekdays.
* **Deposit type:** `Non Refundable` bookings show much lower cancellation rates compared to `No Deposit` or `Refundable`.

---

## Visual Examples

The notebook contains sample visualizations including:

* ADR trends over time
* Cancellations by hotel type and deposit type
* Monthly booking distribution and heatmaps
* Customer segment and market source breakdowns

---

## Recommendations (Actionable)

1. Encourage shorter lead-time bookings or introduce low-cost flexibility add-ons for long lead-time bookings to reduce cancellations.
2. Use dynamic pricing for ADR during peak season in resorts and during high-demand weekdays for city hotels.
3. Promote `Non Refundable` options with limited-time discounts to reduce cancellations and secure revenue.
4. Target high-value markets and low-cancellation customer segments with tailored marketing campaigns.
5. Monitor agent and distribution channel performance — prioritize channels with high conversion and low cancellations.

---

## Files in Repository

* `hotel_analysis.ipynb` — Jupyter notebook with full EDA and visualizations
* `data/` — raw and cleaned datasets (if included)
* `requirements.txt` — Python package dependencies
* `README.md` — this file

---

## Contributing

Contributions, issues and feature requests are welcome. Feel free to open an issue or submit a pull request.

---

## License

This project is released under the MIT License. See `LICENSE` for details.

---

## Contact

Abhishek Kumar — [GitHub](https://github.com/Abhishekkumar903)

---

## References

* Kaggle: Hotel Booking Demand Dataset
* Exploratory data analysis and visualization best practices
