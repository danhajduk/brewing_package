
# Home Assistant Fermentation Monitoring

## Overview

This repository contains the configuration files and documentation for monitoring the fermentation process using Home Assistant. The setup includes various inputs, sensors, automations, and scripts to track and manage the fermentation of homebrew, providing insights and alerts throughout the process.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Configuration Files](#configuration-files)
- [Setup Instructions](#setup-instructions)
- [How to Use](#how-to-use)
- [iSpindel Integration](#ispindel-integration)
- [Backup and Restore](#backup-and-restore)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Automated Monitoring**: Tracks key fermentation metrics such as temperature, gravity, and CO2 levels.
- **Alerts and Notifications**: Sends notifications for high temperature, completed fermentation, low battery, and more.
- **Data Reporting**: Automatically reports fermentation data to BrewersFriend every 15 minutes.
- **Custom Dashboards**: Displays all relevant data on a Home Assistant dashboard for easy monitoring.

## Configuration Files

- **[fermentation_inputs.yaml](./fermentation_inputs.yaml)**: Defines inputs such as original gravity, fermentation start time, and toggle switches.
- **[fermentation_sensors.yaml](./fermentation_sensors.yaml)**: Contains sensors for monitoring temperature, gravity, fermentation phase, etc.
- **[fermentation_automations.yaml](./fermentation_automations.yaml)**: Manages automations like starting/stopping fermentation, sending alerts, and updating gravity readings.
- **[documentation](./documentation)**: Contains detailed documentation files for each component.

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   ```

2. **Place Files in the Correct Directory**:
   - Move the YAML files to the appropriate directories in your Home Assistant setup (e.g., `/config` or a `packages` directory if using packages).
   - Ensure that the `.gitignore` file excludes any sensitive files such as `secrets.yaml`.

3. **Configure Your Home Assistant**:
   - Ensure that all necessary sensors (like iSpindel) are integrated into your Home Assistant setup.
   - Customize the automations and inputs according to your brewing needs.

4. **Initialize Git** (if not already done):
   ```bash
   git init
   git add .
   git commit -m "Initial commit of Home Assistant configuration"
   ```

5. **Set Up Remote Repository** (if desired):
   - Add a remote repository to back up your configuration online.

6. **Restart Home Assistant**:
   - After adding the configuration, restart Home Assistant to apply the changes.

## How to Use

### Starting the Fermentation Process

- Toggle the `fermentation_started` input to `on` in your Home Assistant dashboard. This action will begin tracking the fermentation duration and will activate other automations like gravity monitoring and temperature alerts.

### Monitoring Fermentation

- **Dashboard**: Access the Home Assistant dashboard you've set up for fermentation. This dashboard will display real-time data such as current gravity, temperature, CO2 levels, and more.
- **Temperature Monitoring**: The system continuously monitors the fermentation temperature. If the temperature exceeds 29°C for more than 10 minutes, you’ll receive a notification.
- **Gravity Monitoring**: Gravity readings are taken at regular intervals using the iSpindel device. These readings help track the progress of fermentation and estimate when it will be complete.

### Receiving Notifications

- **Temperature Alerts**: If the fermentation temperature becomes too high, you will receive a notification on your mobile device, prompting you to take action to cool down the fermentation.
- **Fermentation Completion**: Once the gravity readings have remained stable for the threshold period and CO2 levels indicate inactivity, a notification will be sent to confirm that fermentation is likely complete.
- **Low Battery Warning**: If the iSpindel’s battery voltage drops below 3.3V, you’ll be alerted to recharge it.

### Reporting Data to BrewersFriend

- Ensure the `report_to_brewersfriend` input is toggled on. When enabled, the system will automatically send the current fermentation data to BrewersFriend every 15 minutes. This includes data such as gravity, temperature, and ambient conditions.

### Stopping the Fermentation Process

- Once fermentation is complete, toggle the `fermentation_started` input to `off`. This action will stop tracking the fermentation duration and deactivate related automations.

### Analyzing Fermentation Data

- Use the graphs and historical data available on your Home Assistant dashboard to analyze the entire fermentation process. You can review how temperature, gravity, and other metrics changed over time.

## iSpindel Integration

This setup uses the iSpindel device to collect real-time fermentation data, including:

- **Fermentation Temperature**: Monitors the temperature of the fermenting brew.
- **Specific Gravity (SG)**: Tracks the gravity throughout the fermentation process to monitor progress and estimate completion.
- **Battery Voltage**: Keeps track of the iSpindel's battery level to ensure continuous monitoring.

The data collected by the iSpindel is integrated into Home Assistant via MQTT, where it is processed by various sensors and automations. The data is also reported to BrewersFriend for additional analysis and record-keeping.

## Backup and Restore

- **Manual Backup**: Use Home Assistant's backup feature to create snapshots of your configuration.
- **Automated Backup**: Consider setting up automated backups using a cron job or Home Assistant's backup feature.

## Contributing

Contributions are welcome! If you have improvements or suggestions, feel free to fork the repository and submit a pull request. Please ensure that your contributions are well-documented and include clear commit messages.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.