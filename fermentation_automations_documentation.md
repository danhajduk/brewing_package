## Automations

### Notify High Fermentation Temperature
- **Trigger**: Temperature exceeds 29°C for more than 10 minutes.
- **Action**: Sends a notification to your mobile device.

### Start Fermentation
- **Trigger**: `fermentation_started` is toggled to `on`.
- **Action**: Sets the current datetime as the start time for fermentation.

### Stop Fermentation
- **Trigger**: `fermentation_started` is toggled to `off`.
- **Action**: Resets the fermentation start time to `0`.

### Update Previous Gravity Reading
- **Trigger**: Every 30 minutes.
- **Action**: Updates the previous gravity reading with the current gravity value.

### Notify When Fermentation Complete
- **Trigger**: Gravity is stable for the defined threshold, and fermentation is inactive.
- **Action**: Sends a notification indicating fermentation is complete.

### Report Data to BrewersFriend
- **Trigger**: Every 15 minutes if `report_to_brewersfriend` is `on`.
- **Action**: Sends the current fermentation data to BrewersFriend.

### Notify When iSpindel Battery is Low
- **Trigger**: iSpindel battery voltage drops below 3.3V.
- **Action**: Sends a notification to your mobile device.

### Notify When Error Sending Data to BrewersFriend
- **Trigger**: Data sending to BrewersFriend fails.
- **Action**: Sends a notification about the failure.

## Scripts

### report_to_brewersfriend
- **Purpose**: Handles the process of sending fermentation data to BrewersFriend.
- **Sequence**:
  1. Sets the BrewersFriend status to "Sending data".
  2. Sends data using a REST command.
  3. Updates the status to "Successfully Sent" or "Failed to Send" based on the response.

## REST Command

### report_to_brewersfriend
- **URL**: `https://log.brewersfriend.com/stream/95c241ab33c0b51e0307ddae67ce602040d12ea5`.
- **Method**: POST.
- **Headers**: Content-Type: application/json.
- **Payload**: Includes data such as original gravity, temperature, ambient temperature, gravity, battery voltage, and CO2 level.
