

========
Overview
========

The watering sensor node WASENO is going to need an embedded platform, some
kind of actuator to turn water on and off, any number of sensors to determine
when to actuate, an electric energy source to power the whole thing, and
a housing, to keep everything dry and protected.


.. contents::
   :local:
   :backlinks: top


-------------------------------------------------------------------------------
Embedded platform
-------------------------------------------------------------------------------

For an embedded platform, we had a few requirements that pointed us in
the Intel Edison's direction:

- measure soil moisture, keep time, and activate actuators.
- expose a RESTful interface to the sensor node, to query sensor data,
  status log and allow manual override.
- connect with the internet using some kind of wireless technology.

The edison might be a bit overkill with it's dual core application processor,
but having an application processor coupled with a microcontroller and the
wifi+bluetooth radio makes this an obvious choice. For prototyping purposes,
the edison with the arduino compatible breakout board is going to be perfect.

This will cost 100 euros by itself. However the Edison module alone will cost
around 50 euros, and there are cheaper breakout boards once we are done
prototyping.


-------------------------------------------------------------------------------
Actuator
-------------------------------------------------------------------------------

The edison board should turn on and off the water flow using some kind of
actuator. Being already familiar with solenoid valves, that's what we will
be using here.

We picked a solenoid valve with 3/4 inch inlet, and 4 3/8 inch outlets.
So it's basically 4 NC (normally closed) solenoid valves rated at 12v 440mA,
that share the water input line like the one you probably have in your
washing machine.

The cost for the actuator we picked was around 30 euros, which is 7.5 euros
per solenoid valve outlet.


-------------------------------------------------------------------------------
Sensors
-------------------------------------------------------------------------------

A soil moisture sensor allows WASENO to water plants when the soil is too
dry to sustain plant life, but also to save water by not watering
when it rains for instance.

Ideally the moisture sensor would use a combination of capacitance and
resistance to measure soil moisture.

The problem with resistance is that even a change in fertilizing technique
would influence the soil's electric resistance, hence the constant need to
calibrate the sensor.

In addition to that, measuring resistance requires passing current between
the probe's leads. If the probe leads are made out of some kind of metal,
that tends to leach into the soil with time, which might be undesirable.

The soil's electric resistance also changes with temperature, which means
that in addition to measuring resistance, we would have to measure soil
temperature to figure out how to compensate value shifts in the final
moisture measurement.

Using soil capacitance, one tends to get better results, with less
variables to worry about.


-------------------------------------------------------------------------------
Energy Source
-------------------------------------------------------------------------------




-------------------------------------------------------------------------------
Housing
-------------------------------------------------------------------------------


Some of the objectives and constraints of the project:

- Be battery powered and solar charged using a 5w, 12v PV panel.
- Manage the available energy in order to actuate the solenoid valves,
  measure regularly soil moisture using capacitance and communicate
  the relevant data gathered intel's IoT analytics website.
- Try to stay below 100 euros per 4 garden regions or plants.



A mobile app will be developped to showcase/demo the watering sensor node.



Project description,
Solution,
