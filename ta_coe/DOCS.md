# CoE to HTTP server

This server allows interaction with a C.M.I. as a CoE device, using a HTTP API.

> When using CoE V2, scaling errors may occur as a new system is used to scale the values.
> In the case of such an error, please create a ticket.

## Configuration

### CoE

#### Receiving messages

To configure CoE, follow these [instructions](https://wiki.fhem.de/wiki/CanOverEthernet) (German) and enter the IP of
your server. The node number on the C.M.I. can be chosen arbitrarily and have no influence on the function of the addon.

#### Sending messages

To send messages the server needs the IP address of the C.M.I. and a CAN node number under which it should be visible in the C.M.I..
These data are configured using the CLI parameters `--coe-ip` and `--coe-node`.

#### Versions

There are two CoE versions, V1 and V2, which can be set via the CLI parameter `--coe-version`.
The default is V1. The version must also be set in the C.M.I.

### HTTP

The web server has no configuration options.

## Usage

The data can be received with a GET request. Since the received data are not cached between server
restarts and the data are transferred from the C.M.I. only piece by piece. It can happen after a restart of the server
that there is no data yet and the request is answered with a status code `204`.

The full API documentation can be found at `/docs`.
