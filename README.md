# ha-alarm-clock
Input Elements:
input_text:
alarm_name:
name: Display name for the input field.
initial: Initial value set to 'My Alarm'.
input_datetime:
alarm_time:
name: Display name for the input field.
has_date: Disabled date input.
has_time: Enabled time input.
input_boolean:
alarm_enabled:
name: Display name for the input field.
initial: Initial state set to 'off'.
alarm_monday, alarm_tuesday, ..., alarm_sunday:
Individual boolean inputs for each day, all initially set to 'off'.
group:
alarm_weekdays:
Group of boolean inputs for weekdays.
alarm_weekend:
Group of boolean inputs for the weekend.
input_select:
alarm_sound:
name: Display name for the input field.
options: List of sound options.
initial: Initial sound set to 'argon'.
alarm_media_player:
name: Display name for the input field.
options: List of media player options.
initial: Initial media player set to 'kitchen_speaker'.
input_number:
alarm_hour:
name: Display name for the input field.
min, max: Range for hours (0-23).
step: Increment step.
mode: Input mode set to 'slider'.
alarm_minute:
Similar configuration for minutes.
Sensors:
sensor:
A template sensor named 'alarm_time' calculates the alarm time based on the input_number values for hour and minute.
Automations:
alarm_clock_001:

Triggered when the current time matches the calculated 'alarm_time' and the alarm is enabled for the current day.
Activates the 'turn_on_alarm' script.
alarm_clock_set_initial_alarm_time:

Triggered when either the input_number for hours or minutes changes.
Sets the initial alarm time in the input_datetime 'alarm_time'.
alarm_clock_update_alarm_time_from_input_datetime:

Triggered when the input_datetime 'alarm_time' changes.
Updates the input_number values for hour and minute.
Scripts:
turn_on_alarm:

If the script is in the 'on' state, it plays the selected media on the chosen media player.
Repeats for 10 times.
Notifies a persistent notification with the alarm details.
turn_off_alarm:

Stops the media player and turns off the 'turn_on_alarm' and 'snooze_alarm' scripts.
snooze_alarm:

Stops the media player, turns off 'turn_on_alarm', waits for 10 minutes, and then turns on 'turn_on_alarm' again.
This YAML configuration defines a flexible alarm system with various customization options. Users can set the alarm time, enable/disable alarms for specific days, choose sounds and media players, and trigger automations based on the alarm time and enabled days.
