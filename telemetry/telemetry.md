# Telemetry
Telemetry module is responsible for reading various sensors scattered through the ecosystem.  

## Physical

- Temperature
- Humidity
- Electromagnetic, IR, radio signal.
- Earthquake
- Gas
- Camera Live feed and recording
- Motion sensor in a defined vector

## Virtual
- Logging
  - Access logs from [Access Manager](/access-manager.md)
  - Error logs from all modules.
  - Hardware level I/O events.
- Load monitor for each individual device.
- Probing for nearby WiFi devices (802.11n compliant). Keeping it in a database and building up a acquaintances index. 

### Acquiring Logs
Logs will be delivered via simple API and http request. Security is not of paramount for this endpoint. API only exposes CREATE/STORE methods. INDEX and DESTROY methods won't be available.

#### Virtual - Access Logs
| Key           | Value Type                 |
|---------------|----------------------------|
| user_id       | int                        |
| role_slug     | string                     |
| permission_id | int                        |
| event_date    | datetime                   |
| result        | boolean (true for ALLOWED) |


#### Virtual - Error Logs

| Key           | Value Type    |
|:------------- |:------------- |
| device_ecosystem_id      | int |
| event_date      | datetime      |
| error_header | string      |
| error_body | string      |

#### Virtual - Hardware Level I/O Events
| Key                 | Value Type                       |
|---------------------|----------------------------------|
| device_ecosystem_id | int                              |
| event_date          | datetime                         |
| action              | boolean (true for system I/O ON) |

### Acquiring Hardware Load Measures


