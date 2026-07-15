## 6.3	Safety function: Restart prevention
The restart prevention function is a safety feature that prevents the robot's speed from automatically recovering or the robot from restarting arbitrarily when it has stopped or decelerated due to a detected moving object. The system determines whether to allow a restart by periodically receiving robot status signals from the robot's safety-related main control system. If the system is in a stopped or decelerated state and receives a restart signal from the robot's safety-related main control system, the robot resumes its original speed. If the system is not in a stopped or decelerated state, or if it does not receive a restart signal from the robot's safety-related main control system, it maintains its current state.<br>
The restart signal is generated only when the motor is turned on after releasing the emergency stop switch on the controller.

 
{% hint style="danger" %} 
Always ensure that no operators are inside the radar detection zone before initiating a restart.
{% endhint %}
