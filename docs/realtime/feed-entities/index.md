<a class="pencil-link" href="https://github.com/google/transit/edit/master/gtfs-realtime/spec/en/feed-entities.md" title="Edit this page" target="_blank">
    <svg class="pencil" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M10 20H6V4h7v5h5v3.1l2-2V8l-6-6H6c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h4v-2m10.2-7c.1 0 .3.1.4.2l1.3 1.3c.2.2.2.6 0 .8l-1 1-2.1-2.1 1-1c.1-.1.2-.2.4-.2m0 3.9L14.1 23H12v-2.1l6.1-6.1 2.1 2.1Z"></path></svg>
  </a>
  
# Feed Entities

GTFS Realtime supports three distinct types of realtime data, that can be
combined witin a single realtime feed. Summaries are given below, with full
documentation given in the relevant section.

## Trip Updates

#### "Bus X is delayed by 5 minutes"

Trip updates represent fluctuations in the timetable. We would expect to receive
trip updates for all trips you have scheduled that are realtime-capable. These
updates would give a predicted arrival or departure for stops along the route.
Trip updates can also provide for more complex scenarios where trips are
canceled, added to the schedule, or even re-routed.

[More about Trip Updates...](trip-updates.md)

## Service Alerts

#### "Station Y is closed due to construction"

Service alerts represent higher level problems with a particular entity and are
generally in the form of a textual description of the disruption.

They could represent problems with:

*   Stations
*   Lines
*   The whole network
*   etc.

A service alert will usually consist of some text which will describe the
problem, and we also allow for URLs for more information as well as more
structured information to help us understand who this service alert affects.

[More about Service Alerts...](service-alerts.md)

## Vehicle Positions

#### "This bus is at position X at time Y"

Vehicle position represents a few basic pieces of information about a particular
vehicle on the network.

Most important are the latitude and longitude the vehicle is at, but we can also
use data on current speed and odometer readings from the vehicle.

[More about Vehicle Position updates...](vehicle-positions.md)

## Historical remark on feed types

Early versions of GTFS Realtime Specification required each feed to only contain
single type of entities. An example tool to convert from merged to the
feed-per-type schema is located in the Bliksem Labs [gtfsrt-examples](https://github.com/bliksemlabs/gtfsrt-examples/blob/master/split_by_entitytype.py) GitHub repository.
