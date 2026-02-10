# Phyphox Sensor Analysis

This project documents a complete workflow for collecting, organizing, analyzing, and reporting motion-sensor data from the phyphox app (accelerometer and gyroscope). It is structured to support the course task requirements: data acquisition in multiple conditions, plotting, basic statistics, activity comparison, and simple activity classification.

## Objectives

1. Explore phyphox features and document relevant experiments.
2. Contribute sensor results to the phyphox database and capture screenshots.
3. Record accelerometer and gyroscope data for 60 seconds in:
	 - Low-noise environment
	 - Charging condition (fast/standard charger, battery < 60%)
4. Record motion data during walking, running, and another activity.
5. Plot $x$, $y$, $z$ vs time for each sensor.
6. Trim first/last 1 second and compute mean and standard deviation.
7. Detect/label activities with an automated script.

## Workspace Layout

```
phyphox-sensor-analysis/
├─ data/
│  ├─ static/               # Provided example exports
│  ├─ raw/
│  │  ├─ low_noise/
│  │  ├─ charging/
│  │  ├─ walking/
│  │  ├─ running/
│  │  └─ other_motion/
│  └─ processed/            # Cleaned/trimmed data ready for analysis
├─ plots/
│  ├─ accelerometer/
│  └─ gyroscope/
├─ screenshots/             # App screenshots (results + experiment setup)
├─ report/                  # Final report and references
├─ scripts/                 # Analysis scripts (to be added)
├─ README.md
└─ pyproject.toml
```

## File Naming Conventions

Use consistent file names so automation is easier later:

- **Raw data exports**
	- `accel_g_<condition>_<date>_<device>.csv`
	- `accel_g_<condition>_<date>_<device>.xls`
	- `gyro_<condition>_<date>_<device>.csv`
	- `gyro_<condition>_<date>_<device>.xls`

Example:
- `accel_g_low_noise_2026-02-10_pixel7.csv`
- `gyro_charging_2026-02-10_pixel7.xls`

- **Processed data**
	- `accel_g_<condition>_<date>_<device>_trimmed.csv`
	- `gyro_<condition>_<date>_<device>_trimmed.csv`

- **Plots**
	- `accel_g_<condition>_<date>_<device>.png`
	- `gyro_<condition>_<date>_<device>.png`

- **Screenshots**
	- `results_upload_<date>_<device>.png`
	- `experiment_accel_g_<date>_<device>.png`
	- `experiment_gyro_<date>_<device>.png`

## Data Collection Checklist

**App setup and documentation**
- [ ] Install phyphox and explore sensor experiments
- [ ] Find and summarize official usage info (phyphox website/docs)
- [ ] Contribute a result to the phyphox database
- [ ] Screenshot the “Results” tab after submission

**Experiments**
- [ ] Create custom experiment: accelerometer with $g$
- [ ] Create custom experiment: gyroscope
- [ ] Screenshot each experiment setup and results

**Low-noise recording (60 s)**
- [ ] Export accel $g$ data to .csv and .xls
- [ ] Export gyro data to .csv and .xls

**Charging recording (60 s)**
- [ ] Note charger type (fast/standard)
- [ ] Ensure battery < 60%
- [ ] Export accel $g$ and gyro data to .csv and .xls

**Motion activities**
- [ ] Record walking data
- [ ] Record running data
- [ ] Record one additional activity (e.g., stairs, cycling, rotation)
- [ ] Export accel $g$ and gyro data to .csv and .xls

## Analysis Plan (to be scripted later)

1. Load raw exports from [data/raw](data/raw).
2. Clean and standardize columns (time, $x$, $y$, $z$).
3. Remove first/last 1 second from each series.
4. Compute mean and standard deviation for each axis.
5. Plot $x$, $y$, $z$ vs time for accel $g$ and gyro.
6. Compare low-noise vs charging signals.
7. Compare activity signals and characterize patterns.
8. Build a simple activity classifier.

## Reporting

The final report should live in [report](report) and include:

- Summary of phyphox features and documentation sources
- Sensor database contribution details with screenshot
- Experiment setup screenshots and observations
- Plots and statistical tables
- Observations for low-noise vs charging
- Activity comparisons and conclusions
- Classification approach and results

## Notes

- Keep the phone still during low-noise and charging tests.
- Use the same device orientation across recordings if possible.
- If data are noisy, note environmental factors (surface, charger cable, case).

## Status

- Folder structure created.
- Scripts and analysis will be added later.

If you want, I can also add a report template and a data log sheet next.
