# OpenVario Protocol

This document describes the OpenVario serial port protocol.

**Version: 1.2-dev**

## Specification

The OpenVario serial port protocol is built around the `$POV` NMEA sentence:

    $POV,<type>,<value>,<type>,<value>,...*<checksum>
    
A `$POV` sentence can contain multiple datapoints that are defined by `type` and `value`. The `type` part is a letter or number describing the type of the following value according to the following overview of supported types. The `value` part is a floating point number for all currently supported types of datapoints. Future versions of the protocol may support other value types too though.

The list of datapoints should be terminated with the usual asterisk and two character checksum.

## Supported Datapoints

The following section describes all datapoints supported by the current version of the OpenVario protocol.

### Airspeed

* `S`: true airspeed in `km/h`  
  Example: `$POV,S,123.45*05`

### Humidity
* `H`: relative humidity in `%`
  Example: `$POV,H,58.42*24`

### Pressure

* `P`: static pressure in `hPa`  
  Example: `$POV,P,1018.35*39`

* `Q`: dynamic pressure in `Pa`  
  Example: `$POV,Q,23.3*04`

* `R`: total pressure in `hPa`  
  Example: `$POV,R,1025.17*35`

### Temperature

* `T`: temperature in `°C`  
  Example: `$POV,T,23.52*35`

### Vario

* `E`: TE vario in `m/s` 
  Example: `$POV,E,2.15*14`
  
### Wind

* `Wis`: Instantaneous wind speed in `m/s`  
  Example: `$POV,Wis,10.0*01`

* `Wid`: Instantaneous wind direction (true) in `°`  
  Example: `$POV,Wid,243*38`
  
* `Was`: Average wind speed in `m/s`  
  Example: `$POV,Was,10.0*01`

* `Wad`: Average wind direction (true) in `°`  
  Example: `$POV,Wav,243*38`