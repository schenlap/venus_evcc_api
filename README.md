# venus_lapi
Local REST API for victron venus. It read values from dbus and make them available vor rest api.
It's intended use is to interact with evcc:
https://github.com/evcc-io/config#solarwatt-myreserve-battery-meter
```
meters:
name battery
- type: custom
  power:
    source: http
    uri: http://127.0.0.1/rest/status
    jq: .power
  soc:
    source: http
    uri: http://127.0.0.1/rest/status
    jq: .soc
```
## original
based on server script from https://gist.github.com/marcellodesales/9e4288f35ac2cc3e1b83#file-formatted
