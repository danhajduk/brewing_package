# Home Assistant Fermentation Monitoring

## Overview

This repository contains the configuration files and documentation for monitoring the fermentation process using Home Assistant. The setup includes various inputs, sensors, automations, and scripts to track and manage the fermentation of homebrew, providing insights and alerts throughout the process.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Configuration Files](#configuration-files)
- [Setup Instructions](#setup-instructions)
- [How to Use](#how-to-use)
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
