# HKG Departure Delay Predictor

Interactive page for our SDST group project **"Severe Weather and Rush Hours: Factors Associated with Occurrence and Duration of Flight Delays at Hong Kong International Airport in 2025"**.

Set a flight's departure hour, season and the day's weather. Two models estimate the chance the flight leaves more than 15 minutes late:

- **Random forest**: 200 trees, max depth 8, at least 200 flights per leaf
- **Logistic regression**: same 10 inputs (hour, season, warning level, rush hour, holiday, weekend, rainfall, trace rain, wind speed, severe weather the day before)

**Data:** 419,813 valid HKG passenger departures, 6 Sep 2021 – 25 Dec 2025 (the archive starts on 6 Sep 2021).
**Out-of-year test:** refitted on 2021–2024 only and scored on all 150,057 flights of 2025: AUC 0.611 (random forest), 0.604 (logistic). The earlier 2025-only models scored 0.575 / 0.578 on Oct–Dec 2025.

The models run entirely in the browser (`index.html`); their parameters were exported from scikit-learn and checked against Python on 3,000 random inputs (max difference < 1e-7).

**Limitations:** weather inputs are whole-day values, only fully known after the day ends, so the page describes how common delays were under these conditions; it is not a live forecast. Sep 2021 – 2022 falls in Hong Kong's quarantine period, when traffic was about a fifth of 2025 levels.

**Sources:** flight records originally compiled by Webb-site.com (CC BY 4.0); weather data from the Hong Kong Observatory.
