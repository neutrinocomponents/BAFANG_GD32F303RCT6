The following changes have been made to the EBICS v0.09 version for the M560:
1. Reduced the button-press duration required for power-off.
2. Added auto-calibration for the torque sensor while moving without pedaling. The "Range" field now displays the number of calibrations performed since startup.
3. Added assist at start proportional to unfiltered pedal pressure.
4. Added a parameter for cadence sensor direction (If, after replacing the torque sensor, the torque reading is normal while stationary but the motor cuts out abruptly while moving, this is the backwards counter has triggered and you need to change the rotation sensor direction. Field "Undervoltage Recovery" 0 = normal direction, 1 = reverse.
5. Implemented a safe Walk mode compatible with the DPC245 display.
6. Reduced throttle power in Eco mode up to 7 km/h for walk assist.
7. Modified the voltage table used for SOC estimation.
8. Cadence resets to zero more quickly.
9. The "cal" field displays selectable information. Toggle through options using the eco-trail-eco-trail-eco sequence (do not press too rapidly). The mode is indicated as the speed 10-20-30-40-50:
	a. Motor temperature
	b. Torque sensor reading
	c. Rider power output
	d. Throttle signal from 0 to 1000
	e. Current setting
10. Added zero current calibration at startup. Power output is now zero when there is no current.
11. Added an experimental "freerun" function. After pedaling stops, the motor continues to spin at low power. It stops if you back backwards or if the speed drops below 5 km/h. It is safe, the brake stops the motor easily. This is useful when using a rigid connection instead of the HFL1426 clutch. It also allows for shifting without pedaling. It is enabled by the “Limp mode SOC limit” field: 0 - off, 1 - on.

Original EBiCS text:
Master Branch is for the hubmotor controller CRA101C with GD32F303RCT6 processor.

This project is under construction. All you are doing with this project is on your own risk. The authors do not accept any liability for damage to property or personal injury!  
It is strongly recommented to use a fuse between controller and battery. 
Basic functions are implemented, a very first release is published. 
The bin file can be flashed with the [Open Bafang Canable Tool](https://github.com/mdi-9/bafang_canable_pro/releases).  

The canable tool can be used to setup most relevant parameters, but some fields have a different meaning than in the original Bafang firmware and some fields have no function at all yet.  

Attention: the button "Torquesensor Calibration" is used to reset all parameters to their default values!  

For discussion visit the [Endless Sphere forum](https://endless-sphere.com/sphere/threads/foc-open-source-firmware-for-bafang-can-bus-controllers-with-gd32f303-processor.128869/)  

![ElectricParameters](/documentation/ElectricParameters.JPG)  
![BatteryParameters](/documentation/BatteryParameters.JPG)  
![MechanicalParameters](/documentation/MechanicalParameters.JPG)  
![DrivingParameters](/documentation/DrivingParameters.JPG)  
![ThrottleParameters](/documentation/ThrottleParameters.JPG)  
![SpeedSettings](/documentation/SpeedSettings.JPG)  
![AssistFullTab](/documentation/AssistFullTab.JPG)  

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
