# Example magnetometer data

Maintained by [Arno Solin](http://arno.solin.fi)

This data set supplements the paper:

* Arno Solin, Manon Kok, Niklas Wahlström, Thomas B. Schön, and Simo Särkkä (2018). **Modeling and interpolation of the ambient magnetic field by Gaussian processes**. *IEEE Transactions on Robotics*, 34(4):1112–1127. [[arXiv pre-print](http://arxiv.org/abs/1509.04634)] [[DOI](https://doi.org/10.1109/TRO.2018.2830326)]

## Summary

This repository contains magnetometer data that was collected for the experiment illustrated in the video below.

[![Video abstract](https://img.youtube.com/vi/enlMiUqPVJo/0.jpg)](http://www.youtube.com/watch?v=enlMiUqPVJo)

[Link to video on YouTube](http://www.youtube.com/watch?v=enlMiUqPVJo)


## Description

We used a robot for collecting the data (see paper for a detailed sketch). The robot was built on a DiddyBorg (PiBorg Inc., UK, http://www.piborg.org) robotics board, controlled by a Raspberry Pi 2 (model B) single-board computer (Raspberry Pi Foundation, UK, http://www.raspberrypi.org). During data collection, we controlled the robot over Bluetooth with a joystick.

The robot was equipped with a 9-dof MPU-9150 Invensense IMU unit that was sampled at 50 Hz.  The data were collected and stored internally on the Raspberry Pi. Additionally we also collected data from a Trivisio Colibri wireless IMU (TRIVISIO Prototyping GmbH, http://www.trivisio.com), sampled at 100 Hz, and a Google Nexus 5 smartphone (AKM AK8963 3-axis magnetometer), sampled at 50 Hz. To reduce disturbances caused by the robot, the sensors were mounted on an approximately 20 cm thick layer of Styrofoam. The data has been post-processed, the sensor positions and alignments on the robot have been corrected for.

High-accuracy location and orientation reference measurements were provided through the use of a Vicon real-time tracking system. The task was to map the magnetic field inside a marked region roughly 6 m x 6 m in size. The size of the region was limited by the field of view of the Vicon system. The magnetometers were calibrated in the beginning of the measurement session by rotating the robot around all of its axes. A standard spherical calibration approach was used. Due to limits in acquisition length of the Vicon system, we captured the data in parts, each roughly three minutes in length. The magnetic environment remained unchanged for the first five data sets, and later on changes in the field were initiated by bringing in large metallic toolbox shelves.

## Data structures

The data is stored in CSV files that are named `[sensor name]/[seq-num]-[time/mag/loc].csv`, where

* `sensor name`: one of the three sensors being used (Invensense/Trivisio/Nexus).
* `seq num`: The sequence (trial) number. NB: The magnetic field can be assumed stationary only in the first ones. The later ones include metallic objects being brought in to the observation area, see paper.
* `time`: Sample timings in seconds since start of that trial.
* `loc`: Spatial 2D location (meters) of the sensor with rows corresponding to the timings in `time`.
* `mag`: 3-axis magnetometer observations with rows corresponding to the timings in `time`.

The data has been pre-processed: (i) magnetometer calibration has been applied, and (ii) the robot orientation changes have been corrected for.

## Attribution

If you use this data, please cite the paper *Modeling and interpolation of the ambient magnetic field by Gaussian processes*.

## Disclaimer

The data is provided *as is* and with the hope of the sequences being useful.

