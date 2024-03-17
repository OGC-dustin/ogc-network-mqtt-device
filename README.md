# OGC.Engineering
### ogc-network-mqtt-device - device development for the OGC Network ( SIMULATOR branch )
developer contact - dustin ( at ) ogc.engineering

---
## Purpose
* The simulator branch provides a python based simulator of devices...

## Interaction
* Clone repository
```
git clone https://github.com/OGC-dustin/ogc-network-mqtt-device.git --branch simulator
git submodule update --init
```
* Execute simulator
    - If no command line options are given you must configure and start the simulation within the program
    - The minimum set of command line options to have simulator automatically start include:
        * "hostname", "broker", "type", and "auto"
```
ogc-network-device-simulator <command line options>
```
## Command line options
```
    -h --help                   print this help information
    -a --auto                   automatically start simulation if enough arguments are given
    -l --loglevel <level>       set the log level threshold
                                    "FATAL" -> "ERROR" -> "WARNING" -> "NOTICE" -> "INFO" ( default ) -> "DEBUG" -> "TRACE"
    -f --logfile <file>         provide a target file to save logs
    -n --name <name>            set name of device ( device mqtt topic )
    -b --broker <broker>        set broker name to connect to
    -t --type <device-type>     set the device type to simulate
                                    bes - basic environmental sensor
                                    bei - basic environmental interaction
                                    bui - basic user interface
    -p --power <cycle-type>     set a mock power cycle
                                    solar - mock a 24 hour solar cycle
                                    dock - mock a docked device being used and returned to charge randomly
                                    steady - mock a device with a constant power supply
```
## Theory of Operation
* A textual user interface ( TUI ) provides the ability to configure and interact with a simulated device
* The simulted device, once started, will attempt to connect and start interacting with an MQTT broker on the OGC Network
* After joining the OGC Network, the simulator will provide simulated sensor information and responses to requests as per its configuration
