# HKG Departure Delay Predictor

Interactive page for our SDST group project **"Severe Weather and Rush Hours: Factors Associated with Occurrence and Duration of Flight Delays at Hong Kong International Airport in 2025"**.

Set a flight's departure hour, season and the day's weather. Two models trained on 2025 HKG departures estimate the chance the flight leaves more than 15 minutes late:

- **Random forest**: 200 trees, max depth 6, at least 200 flights per leaf
- **Logistic regression**: same 10 inputs

Training: 1 Jan – 30 Sep 2025 (113,351 flights). Test: 1 Oct – 25 Dec 2025 (36,706 flights). Test AUC: 0.575 (random forest), 0.578 (logistic).

The models run entirely in the browser (`index.html`); their parameters were exported from the trained scikit-learn models and checked against Python on 3,000 random inputs.

**Limitation:** weather inputs are whole-day values, only fully known after the day ends, so the page describes how common delays were under these conditions in 2025. It is not a live forecast.

**Data:** flight records originally compiled by Webb-site.com (CC BY 4.0); weather data from the Hong Kong Observatory.
