# Moes 4-Button Scene Switch Z2M (TS0044) Blueprint
### Easily Automate TS0044 Devices Paired via Zigbee2MQTT (Z2M)
#
[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fsahilanguralla%2Fmoes_ts0044_z2m_blueprint%2Fblob%2Fmain%2Fmoes_ts0044_blueprint.yaml)
![Moes TS0044 Scene Switch with Box|250x170](https://github.com/sahilanguralla/moes_ts0044_z2m_blueprint/blob/main/moes_ts0044_box.png) ![Zigbee2MQTT Logo|175x175](https://github.com/sahilanguralla/moes_ts0044_z2m_blueprint/blob/main/z2m_logo.png)

## Description
This blueprint is designed for the Moes 4-Button Scene Switch (TS0044), integrated with Zigbee2MQTT. It condenses all 12 unique button actions for a Scene Switch into a single, easy-to-maintain automation. It supports the following actions for each button:

- **Single Press** -- single_press
- **Double Press** -- double_press
- **Hold** -- hold_press

This blueprint allows you to quickly and easily configure multiple actions for each button on the scene switch, making it a versatile tool for managing your smart home devices.

## Prerequisites

Ensure your device is properly integrated with Zigbee2MQTT. You'll need to locate the MQTT topic associated with your scene switch before setting up the blueprint.

#### *Note*: 
* To expose the actions in Z2M for use in Home Assistant automations, I needed to manually select each button/action on the Scene Switch (e.g., single-click, double-click, and hold every button on the device following initial pairing with Z2M). Without this step, Home Assistant didn't seem to recognize the actions in the automation YAML. 

* If you run into this issue, try this out to see if the actions are exposed and registered in Home Assistant. If that doesn't work, try trailing the Z2M logs and monitor action payloads to that MQTT topic. Every payload reference for each value_template in the YAML below should match the actions exposed by your device.

#### Steps to find your device's MQTT topic:

1. Navigate to the Zigbee2MQTT integration in Home Assistant.
2. Select "Logs" from the ribbon header.
3. Press any button on your Moes Scene Switch.
4. Locate the latest log entry and note the MQTT topic displayed.

## Device Information:
![Moes TS0044 Scene Switch|250x250](https://github.com/sahilanguralla/moes_ts0044_z2m_blueprint/blob/main/moes_ts0044_switch.png)

- **Manufacturer**: Moes (Tuya)
- **Device Type**: 4-Button Scene Switch
- **Model**: TS0044
- **Zigbee Manufacturer**: _TZ3000_wkai4ga5
- **Zigbee2MQTT Device Info**: [Link to TS0044](https://www.zigbee2mqtt.io/devices/TS0044.html)
- **Switch Button Action Correlations**:
    1. Top-Left
    2. Top-Right
    3. Bottom-Left
    4. Bottom-Right

## How to Use

1. **Import the Blueprint**: [Click to Import Blueprint](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fsahilanguralla%2Fmoes_ts0044_z2m_blueprint%2Fblob%2Fmain%2Fmoes_ts0044_blueprint.yaml) or select the "Import Blueprint" button at the top of this post.
2. **Configure**: Use the MQTT topic you found earlier in the "switch_topic" field. Assign actions to each button press (single, double, or hold) using the blueprint inputs.
3. **Test**: Save and test your automation. If you run into any issues, feel free to leave a comment below.
