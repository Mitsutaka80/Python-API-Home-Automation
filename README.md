# Device Registry Service

## Usage 

All responses will have the form 

```json
{
    "data": "Mixed type holding the content of the response",
    "message": "Description of what happned"
}
```

Subsequent response definitions will only detail the expected value of the 'data field' 
<br />
<br />

### List all devices

***Definition***

`GET /devices`

***Response***

- `200 OK` on success

```json
[
    {
        "identifier":"floor-lamp",
        "name": "Floor Lamp",
        "device_type": "switch",
        "controller_gateway": "192.1.68.0.2"
    },
    {
        "Identifier": "samsung-tv",
        "name": "Living Room TV",
        "device_type": "tv",
        "controller_gateway": "192.168.0.9"
    }
]
```

<br />

### Resistering a new device 

***Definition*** 

`POST/devices`

***Arguments***

- `"identifer":string` a globally unique identifier for this device
- `"name":string` a friendly name for this devuce 
- `"device_type":string` the type of the device as understood by the client 
- `"controller_gateway::string` the IP address of the device's controller

If a device with the given identifier already exists, the exsting device will be overwritten. 

***Response***

- `201 Created` on success

```json
{
    "identifier":"floor-lamp",
    "name": "Floor Lamp",
    "device_type": "switch",
    "controller_gateway": "192.1.68.0.2"
}
````






