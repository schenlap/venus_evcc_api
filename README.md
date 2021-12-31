# venus_evcc_api
It's intended use is to interact with evcc and reads values via dbus from victron venus device.
Evcc is running on venus so dbus can be local reads. The kostal pico entries are from https://github.com/schenlap/venus_kostal_pico
```
meters:
- name: grid
  type: custom
  power:
    source: script
    cmd: /bin/sh -c "./get_grid_meter"
- name: battery
  type: custom
  power:
    source: script
    cmd: /bin/sh -c "./get_battery_power" # - ist Bezug bei Victron
    scale: -1
  soc:
    source: script
    cmd: /bin/sh -c "./get_battery_soc"
- name: pv
  type: custom
  power:
    source: calc
    add:
    - source: script
      cmd: /bin/sh -c "./get_solar_power mppt"
    - source: script
      cmd: /bin/sh -c "./get_solar_power Kostal_Pico_5_5"
    - source: script
      cmd: /bin/sh -c "./get_solar_power Kostal_Pico_8_3"
```
