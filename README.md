# Home Assistant IKEA TRADFRI Remote Control Blueprints

This repository contains Home Assistant blueprints for controlling lights using IKEA TRADFRI 4-button remote controls (Remote Control N2) connected via ZHA (Zigbee Home Automation).

## Blueprints

### 1. anna-on-off-and-dim.yaml

**Purpose:** Basic light control with on/off and dimming functionality

**Features:**
- **Up button:** Turn on lights (with optional forced brightness setting*)
- **Down button:** Turn off lights
- **Hold up/down buttons:** Smoothly adjust brightness
- **Left/right buttons:** Customizable short and long press actions for scenes or other automations

*Force brightness: When enabled, lights always turn on at a configured brightness level instead of remembering the last setting.

**Configuration Options:**
- Force brightness on/off
- Default brightness level (0-100%)
- Dimming speed (0.1-2.0 seconds)
- Custom actions for left/right button presses

**Best For:** Simple light control with dimming and custom scene triggers

---

### 2. anna-color-lights.yaml

**Purpose:** Advanced color light control with hue and saturation adjustment

**Features:**
- **Up button:** Turn on lights (with optional forced brightness setting*)
- **Down button:** Turn off lights
- **Hold up/down buttons:** Increase/decrease brightness
- **Right button:** Press to step through hues, hold to continuously cycle
- **Left button:** Press to step through saturation, hold to continuously adjust

*Force brightness: When enabled, lights always turn on at a configured brightness level instead of remembering the last setting.

**Configuration Options:**
- Force brightness on/off
- Default brightness level (0-100%)
- Update speed when buttons are held (0-1000 milliseconds)
- Color hue step size (1-360°)
- Color saturation step size (1-100%)

**Best For:** RGB/RGBW color-changing lights where you want direct control over hue and saturation

---

### 3. anna_temperature.yaml

**Purpose:** Color temperature control for white spectrum lights

**Features:**
- **Up button:** Turn on lights (with optional forced brightness setting*)
- **Down button:** Turn off lights
- **Hold up/down buttons:** Increase/decrease brightness
- **Hold left/right buttons:** Continuously adjust color temperature (left=warmer, right=cooler)
- **Press left/right buttons:** Custom short press actions (Can be used to steer another device, e.g. on/off of a Control Outlet -> configured when creating the automation in the GUI)

*Force brightness: When enabled, lights always turn on at a configured brightness level instead of remembering the last setting.

**Configuration Options:**
- Force brightness on/off
- Default brightness level (0-100%)
- Update speed when buttons are held (0-1000 milliseconds)
- Temperature step size (1-205 mired)
- Custom actions for left/right button short presses

**Best For:** Tunable white lights or lights with adjustable color temperature (warm white to cool white)

---

## Installation

1. Copy the desired blueprint YAML file to your Home Assistant `blueprints/automation` directory
2. In Home Assistant, go to **Settings** → **Automations & Scenes** → **Blueprints**
3. Click **Import Blueprint** and select the copied file
4. Create a new automation using the imported blueprint

## Requirements

- Home Assistant with ZHA integration enabled
- IKEA TRADFRI 4-button Remote Control N2 paired via ZHA
- Compatible light entities (requirements vary by blueprint)

## Compatibility

All blueprints are designed for:
- **Integration:** ZHA (Zigbee Home Automation)
- **Manufacturer:** IKEA of Sweden
- **Model:** Remote Control N2 (4-button square remote)

## Credits

These blueprints are based on community contributions:
- Original work by [frenck](https://community.home-assistant.io/u/frenck)
- Extended by [SwerveShot](https://community.home-assistant.io/u/SwerveShot)
- Temperature control based on [niro1987's work](https://github.com/niro1987/homeassistant-config)
- Color lights based on [cehberlin's gist](https://gist.github.com/cehberlin/be7b5d34aecb71aea0dd9514651e802d)
