---
layout: post
title: "[mobile system] Reactive Control of Autonomous Drones"
comments: true
description: "drone"
keywords: "mobile system, drone, reactive control"
author: Junjue Wang
---

> [PDF](http://dl.acm.org/citation.cfm?id=2906410)

# Summary
The authors conceive a notion of reactive control that supersedes the time-triggered approach by leveraging the characteristics of existing control logic and of the hardware it runs on. 
Under reactive control, control decisions are taken only upon recognizing the need to.

# Background

## Current Drone Architecture
**Ground-control station (GCS)** configure mission parameters, such as coordinates to cover and actions to take at each waypoint
**Autopilot Software** implements low-level control (PID) *autonomously* driving the drone to the enxt desired coordinate

<img src="{{ site.baseurl }}/posts_image/drone-arch.png">

## Low-level Control
+ Most PID controllers on drones are tuned so that only the Proportional component bear an influence
+ PID controllers run in time-triggered fashion:  every T time units, sensors are probed, control decisions are computed, and commands are sent to the actuators.
<img src="{{ site.baseurl }}/posts_image/ardupilot-control-loop.png">
+ Authors observe that control output doesn't change often
<img src="{{ site.baseurl }}/posts_image/control-output-not-change.png">

# Reactive Control

Authors argue for reactive control. 

> Rather than periodically triggering the control logic, we constantly monitor the navigation sensors and run the control logic only upon recognizing the need to. As a result, reactive control dynamically adapts the control rate.

## Benefits of Reactive control

+ enables more timely and adaptive control decisions
+ spares unnecessary processing, improving the utilization of the hardware
+ lessens the need to overprovision control rates to handle extreme situations

## Challenges

+ What is a “significant” change in the sensor input depends on several factors, including the accuracy of sensor hardware, the physical characteristics of the drone, the control logic, and the granularity of actuator output
+ An indication for running the control logic may originate from different sensors, at different rates, and asynchronously with respect to each other
+ Reactive control must run on resource-constrained embedded hardware

## Solutions
+ Use a logistic regssion based On-line approach to determine how large changes in a sensor constitutes "significant". A small boot time at the beginning of runtime is needed to learn how large of sensor reading changes result in control output changes for each sensor.
+ Sample sensors at the highest frequency available and use hyperperiod to group correlated sensor changes together. A failsafe mode is employed to run the control logic anyhow every 0.1 second.
+ A specially designed reactive programming model is implemented to avoid "callback hell"

# Result

<img src="{{ site.baseurl }}/posts_image/drone-pitch-error-improvement.png">
<img src="{{ site.baseurl }}/posts_image/avg-rate-of-control.png">
<img src="{{ site.baseurl }}/posts_image/flight-time-improvement.png">