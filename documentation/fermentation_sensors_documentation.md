## Sensors

### Statistics Sensors
- **average_fermentation_temperature**
  - **Purpose**: Tracks the average fermentation temperature over the last 24 hours.
  - **Sampling Size**: 100 readings.
  - **Max Age**: 1440 minutes (24 hours).

- **average_humidity**
  - **Purpose**: Tracks the average ambient humidity over the last 24 hours.
  - **Sampling Size**: 100 readings.
  - **Max Age**: 1440 minutes (24 hours).

### Template Sensors
- **is_gravity_stable**
  - **Purpose**: Determines if the gravity reading is stable by comparing the current reading with the previous one.
  - **Logic**: Returns `True` if the readings are the same.

- **abv**
  - **Purpose**: Calculates Alcohol By Volume (ABV) based on the original and current gravity.
  - **Formula**: `(OG - FG) * 131.25`.

- **is_fermentation_active**
  - **Purpose**: Checks if the fermentation is active based on CO2 levels.
  - **Threshold**: 1000 ppm CO2.

- **brewersfriend_status**
  - **Purpose**: Displays the current status of data being sent to BrewersFriend.

- **fermentation_duration**
  - **Purpose**: Tracks the total duration of the fermentation process.
  - **Display**: Shows days, hours, and minutes since the start.

- **ispindel_battery_percentage**
  - **Purpose**: Calculates the iSpindel battery percentage based on voltage.
  - **Formula**: `((Voltage - 3.0) / (4.305 - 3.0)) * 100`.

- **gravity_trend**
  - **Purpose**: Shows the trend in gravity readings over time (SG/hour).
  - **Logic**: Calculated based on the difference between the previous and current gravity readings.

- **estimated_time_to_fg**
  - **Purpose**: Estimates the time remaining until the final gravity is reached.
  - **Formula**: `(Current Gravity - Final Gravity) / Gravity Trend * 24`.

- **fermentation_phase**
  - **Purpose**: Identifies the current phase of fermentation (e.g., Active, Slow, Completed, Not Yet Started).
  - **Logic**: Based on gravity trend, CO2 levels, and duration since start.
