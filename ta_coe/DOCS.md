# CoE to HTTP server

This server allows interaction with a C.M.I. as a CoE device, using a HTTP API.

## Configuration

### CoE

#### Receiving messages

To configure CoE, follow these [instructions](https://wiki.fhem.de/wiki/CanOverEthernet) (German) and enter the IP of

your server. The node number on the C.M.I. can be chosen arbitrarily and have no influence on the function of the addon.

#### Sending messages

To send messages the server needs the IP address of the C.M.I. and a CAN node number under which it should be visible in the C.M.I..

These data are configured using the CLI parameters `--coe-ip` and `--coe-node`.

### HTTP

The web server has no configuration options.

## Usage

The data can be received with a GET request. Since the received data are not cached between server

restarts and the data are transferred from the C.M.I. only piece by piece. It can happen after a restart of the server

that there is no data yet and the request is answered with a status code `204`.

The full API documentation can be found at `/docs`.
