

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

When installing an automated irrigation or watering system, installing extra
electrical installation can be one of deal breakers. On top of the water
installation, you would need extra wires to deliver power to valves
and sensors.

To make it possible for our watering sensor nodes to be truly modular and
decoupled from electrical installation restraints, we thought we would
use a small solar panel coupled to a lithium battery to meet the energy
requirements of a sensor node.

The embedded platform needs to be powered up, and consumes less than 1W.
The biggest energy requirement is that of the solenoid valves consuming
5.28W per solenoid. That puts the peak consumption at 22W if we activate
all 4 solenoids at once.

However if we program our mcu to activate one solenoid at a time, we can reduce
peak power requirement to 6W.

With a 14,8v li-ion battery pack (4*3.7v), and a 12v, 5W solar panel, we
should be able to power a watering node.

The arduino breakout board can be directly powered by the pack, since the DC
power jack is rated at 7V–15V DC input.

If there are ways to reduce power consumption, it would be by chosing more
energy efficient water valve actuators to do so.


-------------------------------------------------------------------------------
Housing
-------------------------------------------------------------------------------

For the housing, we know that water and electricity mix badly. We want to
keep the electronic components dry, so the housing needs to be waterproof.




Some of the objectives and constraints of the project:

- Manage the available energy in order to actuate the solenoid valves,
  measure regularly soil moisture using capacitance and communicate
  the relevant data gathered intel's IoT analytics website.
- Try to stay below 100 euros per 4 garden regions or plants.



A mobile app will be developped to showcase/demo the watering sensor node.



Project description,
Solution,
