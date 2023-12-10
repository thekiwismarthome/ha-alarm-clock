# Home Assistant Alarm Configuration
## ha-alarm-clock

![image](https://github.com/thekiwismarthome/ha-alarm-clock/assets/134335563/c96d6f0b-19a7-4f58-9db3-c531b105b530)

![image](https://github.com/thekiwismarthome/ha-alarm-clock/assets/134335563/94457236-0661-4a7f-8f91-176305b08532)



This YAML file serves as a Home Assistant configuration for managing alarms. It encompasses various components and functionalities. Below is an overview of key sections:

## Input Components

### `input_text`
- Defines names for three alarms (`alarm_1_name`, `alarm_2_name`, `alarm_3_name`).

### `input_datetime`
- Sets up time components for each alarm (`alarm_1_time`, `alarm_2_time`, `alarm_3_time`).

### `input_boolean`
- Manages the state of each alarm (enabled or disabled) and specifies the days of the week for each alarm.

### `input_select`
- Allows users to choose sound and media player options for each alarm.

### `input_number`
- Provides sliders for setting the hour and minute for each alarm.

## Groups

- Groups `input_boolean` entities for each alarm into weekdays and weekends.

## Sensors

- Creates template sensors for each alarm, displaying the formatted time.

## Automations

- Sets up automations to trigger alarms based on specified times, considering the day and whether the alarm is enabled.

## Scripts

- Defines scripts to trigger and manage alarms, including turning on, turning off, and snoozing.

## Usage

1. **Integration:** Integrate this configuration into your Home Assistant setup.
2. **Customization:** Customize the configuration as needed, such as adding more alarms or adjusting sound and media player options.

Feel free to explore and adapt this configuration to suit your preferences. For detailed steps on integrating and customizing, refer to the official Home Assistant documentation.

