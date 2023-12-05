# CPX400DP Python Module

## Overview

The CPX400DP Python module provides class for interfacing with CPX400DP power supplies through serial communication via a USB cable. It allows control through a UI when run as \_\_main\_\_ or can be imported into code and can be scripted. It includes features for connecting to a power supply, setting voltage and current values, enabling/disabling channels, and retrieving status information.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Documentation](#documentation)

## Installation

To install the CPX400DP Python module, use the following command:

```bash
pip install CPX400DP
```

## Usage

Eample script:
```py
from CPX400DP import CPX400DP

# Instantiate the CPX400DP class
power_supply = CPX400DP()

com_port = 'COM3'
if com_port is None:
    # Alternately, if only 1 power supply is connected, attempt to autoconnect
    power_supply.autoConnect()
else:
    # Connect to the power supply
    power_supply.connect(com_port)

# Set voltage to 5V and current to 0.5A for the left channel
power_supply.setVoltage(5, channel=1)
power_supply.setCurrent(0.5, channel=1)

# Enable the output
power_supply.enableOutput(channel=1)

# Disable the output
power_supply.disableOutput(channel=1)

# Disconnect from the power supply
power_supply.disconnect() # Note: This does not disable the outputs!!
```

## Documentation

See file for documentation currently. 
