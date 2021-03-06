---
layout: component
title: "Intruder Alerts"
description: "Instructions how to receive intruder alerts from Home Assistant."
date: 2015-01-20 22:36
sidebar: true
comments: false
sharing: true
footer: true
ha_category: Alarm
---


The component `simple_alarm` is capable of detecting intruders. It does so by checking if lights are being turned on while there is no one at home. When this happens it will turn the lights red, flash them for 30 seconds and send a message via [the notifiy component]({{site_root}}/components/notify/). It will also flash a specific light when a known person comes home.

This component depends on the components [device_tracker]({{site_root}}/components/device_tracker/) and [light]({{site_root}}/components/light/) being setup.

To set it up, add the following lines to your `configuration.yaml` file:

```yaml
simple_alarm:
# Example configuration.yaml entry
  known_light: light.Bowl
  unknown_light: group.living_room
```

Configuration variables:

- **known_light** (*Required*): Which light/light group has to flash when a known device comes home.
- **unknown_light** (*Required*): Which light/light group has to flash red when light turns on while no one home.

