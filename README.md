# ha-alarm-clock
## Alarm System Configuration

### Input Elements:

#### `input_text`:
- **alarm_name:**
  - `name`: Alarm Name
  - `initial`: 'My Alarm'

#### `input_datetime`:
- **alarm_time:**
  - `name`: Alarm Time
  - `has_date`: false
  - `has_time`: true

#### `input_boolean`:
- **alarm_enabled:**
  - `name`: Alarm Enabled
  - `initial`: off
- **alarm_monday, alarm_tuesday, ..., alarm_sunday:**
  - Individual boolean inputs for each day, all initially set to 'off'.

#### `group`:
- **alarm_weekdays:**
  - Group of boolean inputs for weekdays.
- **alarm_weekend:**
  - Group of boolean inputs for the weekend.

#### `input_select`:
- **alarm_sound:**
  - `name`: Alarm Sound
  - `options`: List of sound options.
  - `initial`: 'argon'
- **alarm_media_player:**
  - `name`: Alarm Media Player
  - `options`: List of media player options.
  - `initial`: 'kitchen_speaker'

#### `input_number`:
- **alarm_hour:**
  - `name`: Alarm Hour
  - `min`, `max`: Range for hours (0-23).
  - `step`: Increment step.
  - `mode`: Slider input.

- **alarm_minute:**
  - `name`: Alarm Minute
  - `min`, `max`: Range for minutes (0-59).
  - `step`: Increment step.
  - `mode`: Slider input.

### Sensors:

- **sensor:**
  - A template sensor named 'alarm_time' calculates the alarm time based on the input_number values for hour and minute.

### Automations:

- **alarm_clock_001:**
  - Triggered when the current time matches the calculated 'alarm_time' and the alarm is enabled for the current day.
  - Activates the 'turn_on_alarm' script.

- **alarm_clock_set_initial_alarm_time:**
  - Triggered when either the input_number for hours or minutes changes.
  - Sets the initial alarm time in the input_datetime 'alarm_time'.

- **alarm_clock_update_alarm_time_from_input_datetime:**
  - Triggered when the input_datetime 'alarm_time' changes.
  - Updates the input_number values for hour and minute.

### Scripts:

- **turn_on_alarm:**
  - If the script is in the 'on' state, it plays the selected media on the chosen media player.
  - Repeats for 10 times.
  - Notifies a persistent notification with the alarm details.

- **turn_off_alarm:**
  - Stops the media player and turns off the 'turn_on_alarm' and 'snooze_alarm' scripts.

- **snooze_alarm:**
  - Stops the media player, turns off 'turn_on_alarm', waits for 10 minutes, and then turns on 'turn_on_alarm' again.


