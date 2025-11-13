# Home Assistant Automations

A collection of automation blueprints and YAML scripts for Home Assistant to streamline your smart-home routines.

## Overview

This repository provides ready-to-use automations and blueprint templates designed to work with **Home Assistant’s automation engine**.  
These scripts simplify common use-cases such as remote-controlled lighting, color effects, and smart-button mappings.

All automations are written in **YAML** and can be placed in your `automations/` or `blueprints/automation/` folder (as specified in each file).

---

## Included Automations & Blueprints

### `color_loop_christux.yaml`
Cycles through a defined list of colors on a target light or group at a configurable interval.  
Useful for ambient lighting, notifications, or party effects.

**Parameters:**
- `light_entity`: target light(s)
- `interval`: time between color changes
- `brightness`: optional brightness setting
- `colors`: list of RGB or named colors

---

### `zha_ikea_tradfri_4button_remote_color_tux.yaml`

Automation for the **IKEA TRÅDFRI 4-button remote (ZHA integration)**, designed for **RGBW** bulbs or strips where the **white temperature and color modes are exclusive** (cannot be active at the same time).  

This automation maps the remote’s buttons to intuitive lighting controls that replicate native IKEA behavior — while adding color-mode logic and adjustable speed for smooth transitions.

#### Button Mapping

| Button | Action | Short Press | Long Press |
|:--|:--|:--|:--|
| **Top** | Power / Brightness ↑ | Turn **on** the light | Gradually **increase brightness** |
| **Bottom** | Power / Brightness ↓ | Turn **off** the light | Gradually **decrease brightness** |
| **Right** | **Color mode** | Switch to **color mode** and cycle to the next color | Cycle colors **faster** |
| **Left** | **White mode** | Switch to **white mode** and change color temperature | Change temperature **faster** |

#### Behavior Details

- The light operates in two **mutually exclusive modes**:  
  - **Color mode (RGB)** for rich colors.  
  - **White mode (CCT)** for adjustable white temperatures.  
- Switching to one mode automatically disables the other.  
- Brightness changes are smooth and continuous when a button is held.  
- Long presses on color or white mode buttons accelerate transitions for a more dynamic feel.  

**Parameters:**
- `remote`: ZHA remote entity ID  
- `target_light`: entity or group controlled  
- `brightness_step`: amount of brightness change per press  
- `color_cycle_speed`: delay between color transitions  

---

## Acknowledgements

Special thanks to the authors and community members whose scripts and discussions inspired these automations.

- [Orce MARINKOVSKI / [Link](https://gist.github.com/orcema/c282c72ddc549060fb10999dbe774526)]  
- [Malte / [Link](https://community.home-assistant.io/t/zha-ikea-four-button-remote-styrbar-for-lights-e2001-e2002/384482)]  
- [Damien Rubio / [Link](https://gist.github.com/damru/19ac1c8530cf744595a9e239cf5bb20f)]  
- [hugalafutro / [Link](https://gist.github.com/hugalafutro/07a15a55d1e8394744e423a9ce7c8223)]
