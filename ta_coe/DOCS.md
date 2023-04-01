# CoE to HTTP server

This addon receives incoming CoE messages from a C.M.I. and makes them available via HTTP Api.

## Configuration

### CoE

To configure CoE, follow these [instructions](https://wiki.fhem.de/wiki/CanOverEthernet) (German) and enter the IP of your Home Assistant instance. The node number can be chosen arbitrarily and have no influence on the function of the addon.

The port of the CoE server should not be changed, otherwise no data can be received.

### HTTP

The web server has no configuration options except for the port.

Port forwarding is disabled by default to allow only requests within Home Assistant.

## Usage

The data can be received with a GET request to the path `/`. Since the received data are not cached between addon restarts and the data are transferred from the C.M.I. only piece by piece. It can happen after a restart of the addon that there is no data yet and the request is answered with a status code `204`.

## Data structure

The provided data has the following structure:

```json
{
  "digital": [
    {
      "value": true,
      "unit": 43
    }
  ],
  "analog": [
    {
      "value": 34.4,
      "unit": 1
    }
  ],
  "last_update_unix": 1680410064.03764,
  "last_update": "2023-04-01T12:00:00"
}


```
