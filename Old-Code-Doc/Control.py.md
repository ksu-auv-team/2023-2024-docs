### Introduction
The `const.py` file serves as a central location where system constants referenced throughout the project are defined. This approach facilitates easier adjustments and tweaks to the constants as needed.
### Constants Defined
1. **FLIP_RUN**: A boolean value indicating whether the run should be flipped left-to-right. It is expected to be changed per run depending on the part of the pool the AUV is in. `True` indicates left-turning, while `False` indicates right-turning.
2. **DEFAULT_MSG_AXES**: A tuple representing the default joystick message values for axes.
3. **DEFAULT_MSG_BUTTONS**: A tuple representing the default joystick message values for buttons.
### Enumerations
1. **AXES**: A dictionary mapping various joystick axes to their respective indices in the axes tuple. The keys and their respective mappings are as follows:
    - `'rotate'`: Index 0, with a range from -1.0 (rotates right) to 1.0 (rotates left).
    - `'vertical'`: Index 1, with a range from -1.0 (sinks) to 1.0 (ascends).
    - `'lt'`: Index 2.
    - `'strafe'`: Index 3, with a range from -1.0 (strafe right) to 1.0 (strafe left).
    - `'frontback'`: Index 4, with a range from -1.0 (backwards) to 1.0 (forwards).
    - `'rt'`: Index 5.
    - `'dpad_h'`: Index 6.
    - `'dpad_v'`: Index 7.
2. **BUTTONS**: A dictionary mapping various joystick buttons to their respective indices in the buttons tuple.
3. **CLASSES**: A dictionary mapping various classes to their respective indices. It seems to be used for object classification in image processing tasks.
### Joystick Messages Function Map
1. **JOY_MAP**: A dictionary mapping functions to configured buttons on the joystick.
### Launcher Geometric Offsets
1. **LAUNCHER_LEFT_OFFSET** and **LAUNCHER_RIGHT_OFFSET**: Dictionaries defining the geometric offsets to apply just before launching a torpedo. They contain keys `'WINDAGE_OFFSET'` and `'ELEVATION_OFFSET'` to define the horizontal and vertical offsets, respectively.
2. **CAMERA_FORWARD_CENTER** and **CAMERA_UNDER_CENTER**: Dictionaries defining the geometric centers of the forward and under cameras, respectively.
3. **SLEEP_TIME**: A constant defining the amount of time (in seconds) to sleep before looking for another frame.
### Usage Examples
The file also contains usage examples demonstrating how to use the AXES and BUTTONS enumerations to create joystick messages and publish them.
### Conclusion
The `const.py` file centralizes the definition of various constants and enumerations used throughout the project, facilitating easier adjustments and a clearer understanding of the joystick controls and object classifications.