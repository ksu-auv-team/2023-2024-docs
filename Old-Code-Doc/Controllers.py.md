### Introduction
The `controllers.py` file contains implementations of various control algorithms, namely PID, PI, PD, and P controllers. These controllers are generalized for application in various parts of the codebase and are essential in controlling the behavior of the AUV (Autonomous Underwater Vehicle).
### Classes Defined
1. **PID Controller**
    - **Attributes**:
        - `kp`: Proportional constant coefficient.
        - `ki`: Integral constant coefficient.
        - `kd`: Derivative constant coefficient.
        - `I`: Integral value.
        - `I_max`: Maximum integral value.
        - `I_min`: Minimum integral value.
        - `D`: Derivative value.
        - `set_point`: The target value for the control system.
    - **Methods**:
        - `Update(current_value)`: Calculates the controlled output for the updated input value. It computes the error between the set point and the current value and calculates the proportional, integral, and derivative values to determine the controlled output.
2. **PI Controller**
    - **Attributes**:
        - `kp`: Proportional constant coefficient.
        - `ki`: Integral constant coefficient.
        - `I`: Integral value.
        - `I_max`: Maximum integral value.
        - `I_min`: Minimum integral value.
        - `set_point`: The target value for the control system.
    - **Methods**:
        - `Update(current_value)`: Similar to the PID controller but without the derivative component.
3. **PD Controller**
    - **Attributes**:
        - `kp`: Proportional constant coefficient.
        - `kd`: Derivative constant coefficient.
        - `D`: Derivative value.
        - `set_point`: The target value for the control system.
    - **Methods**:
        - `Update(current_value)`: Similar to the PID controller but without the integral component.
4. **P Controller**
    - **Attributes**:
        - `kp`: Proportional constant coefficient.
        - `set_point`: The target value for the control system.
    - **Methods**:
        - `Update(current_value)`: A simple controller that only uses the proportional component to calculate the controlled output.
### Conclusion
The `controllers.py` file houses the implementations of various control algorithms that are fundamental in achieving precise control over the AUV's behavior. Understanding these controllers is vital in tweaking and optimizing the AUV's performance.