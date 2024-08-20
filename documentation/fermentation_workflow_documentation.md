## Workflow

1. **Start Fermentation**: 
   - Toggle `input_boolean.fermentation_started` to `on`.
   - The system begins tracking the start time, temperature, gravity, and other fermentation metrics.

2. **Monitor Fermentation**:
   - Automations monitor key metrics such as temperature and gravity.
   - Notifications are sent if the temperature exceeds safe levels or if the iSpindel battery is low.
   - Data is sent to BrewersFriend every 15 minutes if reporting is enabled.

3. **Complete Fermentation**:
   - The system checks for gravity stability and CO2 levels.
   - Once the gravity is stable and fermentation is inactive, a notification is sent to indicate completion.

4. **Troubleshooting**:
   - If the fermentation duration isn't updating, ensure that `fermentation_started` is `on`.
   - For any issues with data reporting, check the BrewersFriend status for errors.

## Backup and Restore

### Creating Backups
- **Manual Backup**: Go to **Settings** > **System** > **Backups** and create a new backup.
- **Automated Backups**: Set up automated backups using the Home Assistant Supervisor.

### Restoring Backups
- **Restore Process**: Navigate to **Settings** > **System** > **Backups** and select the backup you want to restore from.

## Version Control

### Using Git
- **Track Changes**: Use Git to track changes to your configuration files. Commit regularly with clear messages.
- **Example Commit Message**: "Updated gravity trend calculation and added new notification automation."
