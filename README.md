
# Dont't use this

Please use the node red flow below as this no longer works!
<details><summary>Code in here</summary>
<p>

```json
[
    {
        "id": "54d3ffb5afde5026",
        "type": "tab",
        "label": "Entity updater github",
        "disabled": false,
        "info": "",
        "env": []
    },
    {
        "id": "9748b7d3ee3d573f",
        "type": "delay",
        "z": "54d3ffb5afde5026",
        "name": "",
        "pauseType": "delay",
        "timeout": "1",
        "timeoutUnits": "seconds",
        "rate": "1",
        "nbRateUnits": "1",
        "rateUnits": "second",
        "randomFirst": "1",
        "randomLast": "5",
        "randomUnits": "seconds",
        "drop": false,
        "outputs": 1,
        "x": 560,
        "y": 240,
        "wires": [
            [
                "db75848c5ebd9458"
            ]
        ]
    },
    {
        "id": "db75848c5ebd9458",
        "type": "api-call-service",
        "z": "54d3ffb5afde5026",
        "name": "Update Spotify",
        "server": "fc763be4.baeb38",
        "version": 3,
        "debugenabled": false,
        "service_domain": "homeassistant",
        "service": "update_entity",
        "entityId": "",
        "data": "",
        "dataType": "jsonata",
        "mergecontext": "",
        "mustacheAltTags": false,
        "outputProperties": [],
        "queue": "none",
        "x": 740,
        "y": 240,
        "wires": [
            [
                "a1e6962d3a293394"
            ]
        ]
    },
    {
        "id": "a1e6962d3a293394",
        "type": "delay",
        "z": "54d3ffb5afde5026",
        "name": "",
        "pauseType": "delay",
        "timeout": "1",
        "timeoutUnits": "seconds",
        "rate": "1",
        "nbRateUnits": "1",
        "rateUnits": "second",
        "randomFirst": "1",
        "randomLast": "5",
        "randomUnits": "seconds",
        "drop": false,
        "outputs": 1,
        "x": 900,
        "y": 240,
        "wires": [
            [
                "9748b7d3ee3d573f"
            ]
        ]
    },
    {
        "id": "ab406a1279b93f64",
        "type": "inject",
        "z": "54d3ffb5afde5026",
        "name": "HASS Connected?",
        "props": [
            {
                "p": "payload"
            },
            {
                "p": "topic",
                "vt": "str"
            }
        ],
        "repeat": "1",
        "crontab": "",
        "once": false,
        "onceDelay": 0.1,
        "topic": "",
        "payload": "homeassistant.homeAssistant.isConnected",
        "payloadType": "global",
        "x": 110,
        "y": 240,
        "wires": [
            [
                "046e30028a8f7ab1"
            ]
        ]
    },
    {
        "id": "046e30028a8f7ab1",
        "type": "rbe",
        "z": "54d3ffb5afde5026",
        "name": "",
        "func": "rbei",
        "gap": "",
        "start": "",
        "inout": "out",
        "septopics": true,
        "property": "payload",
        "topi": "topic",
        "x": 280,
        "y": 240,
        "wires": [
            [
                "3d2b99bebc2f1d40"
            ]
        ]
    },
    {
        "id": "3d2b99bebc2f1d40",
        "type": "switch",
        "z": "54d3ffb5afde5026",
        "name": "",
        "property": "payload",
        "propertyType": "msg",
        "rules": [
            {
                "t": "true"
            },
            {
                "t": "else"
            }
        ],
        "checkall": "false",
        "repair": false,
        "outputs": 2,
        "x": 400,
        "y": 240,
        "wires": [
            [
                "9748b7d3ee3d573f"
            ],
            []
        ]
    },
    {
        "id": "fc763be4.baeb38",
        "type": "server",
        "name": "Home Assistant",
        "version": 2,
        "addon": true,
        "rejectUnauthorizedCerts": true,
        "ha_boolean": "y|yes|true|on|home|open",
        "connectionDelay": true,
        "cacheJson": true,
        "heartbeat": false,
        "heartbeatInterval": 30
    }
]
```
    
</p>
</details>

# Spotify-custom-scan-interval
Home Assistant Spotify integration with 1 second scan interval. 
Don't use this because it's really messed up lol.
Download the folder "spotify" and add it to custom_components or, add this repository to HACS.
You can still use "spotify" in configuration.yaml
