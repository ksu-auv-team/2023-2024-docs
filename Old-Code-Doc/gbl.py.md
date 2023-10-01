### Introduction
The `gbl.py` file serves as a repository for global variables and functions that are accessed throughout the subdriver module. These variables hold vital information about the AUV's state and the environment it is operating in.
### Global Variables
1. **run_start_time**: Holds the time at the start of the run. It is not initialized at the beginning and expected to be set at the start of the AUV's operation.
2. **depth**: Represents the current depth of the AUV in meters. This value is updated by the `vfr_hud_callback()` function based on the data from the depth sensor.
3. **init_depth**: Stores the depth at the beginning of the run, which is the depth at the surface. This is used to account for variations in atmospheric pressure.
4. **heading**: Represents the current compass heading in degrees, ranging from 0 to 360. This value is updated by the `vfr_hud_callback()` function.
5. **init_heading**: Stores the compass heading at the beginning of the run.
6. **state_heading**: Holds the compass heading at the beginning of the current state or set of states. This is primarily used for search patterns that span multiple states.
7. **detections_front**: A list that stores detections from the front camera as identified by the neural network. This list is updated by the `bbox_callback_front()` function.
8. **detections_bottom**: A list that stores detections from the bottom camera as identified by the neural network. This list is updated by the `bbox_callback_bottom()` function.
9. **current_target**: Holds the object currently being targeted. It is initialized to `None` and expected to be updated during the operation.
10. **surfacing**: A boolean variable indicating whether the AUV is attempting to surface. When set to `True`, it overrides the depth-limiting code in `sub.publish_joy` to allow the AUV to surface.
11. **debug**: A boolean variable indicating whether the system is in debug mode.
### Conclusion
The `gbl.py` file centralizes the definition of various global variables that are crucial for the operation and control of the AUV. These variables store real-time data about the AUV's state and the environment, facilitating coordinated control and response mechanisms.