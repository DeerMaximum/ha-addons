<!-- https://developers.home-assistant.io/docs/add-ons/presentation#keeping-a-changelog -->

## 2.1.5

- Update dependencies
- Fix voltage scale factor for CoE v2
- Use uv

## 2.1.4

- Fix Overflow Error
- Add logging of HTTP requests in debug mode

## 2.1.3

- Fix wrong data validation on v2 endpoints

## 2.1.2

- Allow negative values in V2 messages
- Update dependencies

## 2.1.1

- Fix to big CoE messages

## 2.1.0

- Add support for CoE version 2

## 2.0.4

- Fixed missing scaling factor for unit 52

## 2.0.3

- Revert scaling factor for unit 2

## 2.0.2

- Fixed missing scaling factor for unit 2
- Fixed missing scaling factor for unit 65

## 2.0.1

- Fixed missing scaling factor for unit 58

## 2.0.0

### Breaking
- GET call to retrieve CAN data now requires a path parameter

### Other
- Add support for receiving multiple CAN-IDs

## 1.1.4

- Add missing unit 24

## 1.1.3

- Fix page mapping

## 1.1.2

- Fix page limit

## 1.1.1

- Fix error with negative analog values

## 1.1.0

### Note
At least the version 1.1.0 for the Technische-Alternative-CoE integration is required for the upgrade.

### Changes

- Add version endpoint

## 1.0.0

### Breaking

- New API paths for receiving data

### Other

- Adding the option to send values to the CMI
- Switch configuration to CLI arguments

## 0.1.1

- Add scale factor for pressure

## 0.1.0

- Extend debug logs

## 0.0.1

- Initial release
