.. development planning (risk management, iteration)


====================
Development planning
====================


.. contents::
   :local:
   :backlinks: top


-------------------------------------------------------------------------------
Risk Management
-------------------------------------------------------------------------------

We won't be doing any elaborate risk analysis or management here. However
knowing where we're heading and prioritizing tasks, requires knowing what
risks are involved, and how they are ordered.

For instance, the development team here has one member who's a CS graduate.
This project however has many aspects that go beyond what would be expected
from a software engineer.


~~~~~~~~
Hardware
~~~~~~~~

The following competence risks were identified ordered from the biggest
to the smallest:

Plumbing
    Little to no experience in plumbing. Not familiar with available tools
    and products, and mistakes can be costly, but can be easily avoided.
Electronics
    Too many new concepts. Unfamiliar parts. Mistakes can be costly and
    not always obvious how to avoid problems.


So we'll start with the plumbing challenges to get rid of the biggest threat
to this project's viability. Then we'll move on to the electronics,
and come up with a plan of action to avoid any unexpected surprises.

The control part seems to be the easiest with the arduino breakout. However
moving to simpler and cheaper breakout boards will introduce the additional
challenge of having to make things work with ``1.8V`` logic.

The software part seems to be the easiest part of the project to deal with.
It will be left for last.


~~~~~~~~
Software
~~~~~~~~

Software wise, the biggest risk is developping the mobile app, since we simply
don't have the required experience. Beyond a simple hello world was
not attempted on android.

However, we do have experience in designing RESTful interfaces, and building
server side components (mainly server side web applications, and application
middleware).

Taking that into consideration, and given that the application's job is the
administration of the various connected WASENOs we decided to go with a mobile
html5 interface for the phone. This might change later, but since access to
the administration device hardware is not required, this seems like an obvious
choice.


-------------------------------------------------------------------------------
Objectives and Constraints
-------------------------------------------------------------------------------

Our BOM (Bill of material) exceeded 25 euros per water output for our first
prototype:

- 100 euros the arduino (provided by the Maker Austria Automation Challenge).
- 16 euros for the industrial outdoor enclosure.
- 19 euros for the 12V, 5W solar panel.
- 30 euros for the 4 solenoid actuators.
- 40 euros in pipes, fittings, cables, cable glands and other misc.

This section will evolve with the project. Right now, the cost is slightly over
double our budget, with 205 euros in parts.


-------------------------------------------------------------------------------
Milestones
-------------------------------------------------------------------------------

~~~~~~~~~
``0.0.1``
~~~~~~~~~

- connects to water line and wifi network.
- activates solenoids individually by following a schedule or manual control.
- administration and control through a mobile-friendly web interface.
- powered by a ``14.8V`` li-ion battery pack.


~~~~~~~~~
``0.0.2``
~~~~~~~~~

- Solve water proofing issues, and have an enclosure ready for physical
  deployment.
- Add moisture sensor reading, and add watering capability based on soil
  moisture.
- Add battery management system, to make solar charging viable and safe.


~~~~~~~~~
``0.0.3``
~~~~~~~~~

- Add a water flow sensor to each water output.
- Review materials used and find cheaper or more ecological alternatives.
- Add intelligence to the sensor software:

  - use of weather predictions web services to adjust the watering cycle.
  - use moisture and flow sensors to detect sensor malfunction.
