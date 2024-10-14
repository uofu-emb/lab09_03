# lab09_03
Here we have the original FSM for the railroad.
![alt text](<Original FSM Train.jpg>)

# Invariants
Certainly! Here’s a table format for the invariants of the safety warning system FSM suitable for a README:

| **Invariant**                | **Description**                                                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| Crossing Safety              | The barrier must always be lowered when a train is approaching or present. It cannot be raised while a train is detected by either proximity sensor.  |
| Alarm State                  | The alarm is either on (sounding) or off (not sounding). It must be on when a train is approaching and continue until 10 seconds after the train departs. |
| Timing Consistency           | The timer starts when the alarm is activated and ensures the barrier lowers only after the alarm has been on for 10 seconds.                           |
| Sequential Events            | The events for a train (northbound_approach and northbound_depart or southbound_approach and southbound_depart) must occur in the correct order.    |
| Exclusive States             | The barrier and alarm states must not conflict; the alarm cannot be off while the barrier is down, and vice versa.                                   |
| State Coherency              | The system must not transition to an unsafe state, ensuring safe sequences are followed during state changes.                                        |



# Varying invariants

We could have a scenario where a south bound train. While the system is in the arms down state we could have a northbound train. This would result in the arms being brought up before the northbound train leaves the crossing. 