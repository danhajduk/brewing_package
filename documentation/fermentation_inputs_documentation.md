# Home Assistant Fermentation Monitoring Configuration

## Overview
This document outlines the configuration for monitoring fermentation using Home Assistant, including inputs, sensors, automations, and scripts.

## Inputs
### Input Numbers
- **gravity_stable_threshold**
  - **Purpose**: Defines the number of hours the gravity must remain stable to consider fermentation complete.
  - **Min/Max Values**: 1 hour to 72 hours.
  - **Unit**: Hours.

- **previous_gravity_reading**
  - **Purpose**: Stores the previous gravity reading for comparison with the current reading.
  - **Min/Max Values**: 0.980 SG to 1.200 SG.
  - **Unit**: Specific Gravity (SG).

- **original_gravity**
  - **Purpose**: Stores the original gravity of the brew, used to calculate ABV.
  - **Min/Max Values**: 1.000 SG to 1.200 SG.
  - **Unit**: Specific Gravity (SG).

### Input Booleans
- **fermentation_started**
  - **Purpose**: Indicates whether the fermentation process has started. When toggled on, it triggers the start of the fermentation duration timer.
  - **Icon**: mdi:play-circle.

- **report_to_brewersfriend**
  - **Purpose**: Controls whether fermentation data should be sent to BrewersFriend. When on, data is sent every 15 minutes.

### Input Datetime
- **fermentation_start_time**
  - **Purpose**: Stores the start time of the fermentation process, used to calculate the total duration.
  - **Date and Time**: Includes both date and time for accurate tracking.
