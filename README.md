# homebridge-philipstv-enhanced-19
Homebridge module for Philips TV (with JointSpace enabled) with Power on/off, Sound, Ambilight and Inputs list & control

# Description

This plugin is a fork of [homebridge-philipstv-x](https://www.npmjs.com/package/homebridge-philipstv-x) with additional support for Sound control, Ambilight brightness control and input selection control.
It has been modified to work on a 55OLED754/12 TV (2019 model with SaphirTV OS witch is not on Android) and may not work on older one. Code may need ajustement for Ambilight to work on other 2018 models

# Installation

1. Install homebridge using: npm install -g homebridge
2. Install this plugin using: npm install -g homebridge-philipstv-enhanced-19
3. Update your configuration file. See the sample below.

# Configuration
 
Example accessory config (needs to be added to the homebridge config.json):
To be able to power on the TV when the TV is in standby mode, you will need the wol_url parameters with the mac address of your TV
Added test option for WakeOnWLAN:

 ```
"accessories": [
    {
        "accessory": "PhilipsTV",
        "name": "TV",
        "ip_address": "10.0.1.23",
        "poll_status_interval": "60",
        "model_year" : "2019",
        "wol_url": "wol://18:8e:d5:a2:8c:66"
        "inputs": [
            {
                "id": "hdmi1",
                "name": "Apple TV"
            },
            {
                "id": "hdmi2",
                "name": "PS4"
            }
        ]
    }
]
 ```

# Dev notes about JointSpace URLs

POST to /6/menuitems/settings/current allow to get current Ambilight settings
POST to /6/menuitems/settings/update allow to update Ambilight settings
GET to /6/menuitems/settings/structure allow to have the details of the menu and options

