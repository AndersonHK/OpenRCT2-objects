# Passenger boarding durations

This fork accepts `boardingDuration` inside each ride car definition (`properties.cars`, or each element when it is an array).
The value is a finite number of simulation seconds from 0 through 30. Omitted or zero means no added settling delay.
It starts when the passenger reaches the boarding position; walking and dispatch waits are separate. Passengers settle
concurrently, with paired seats waiting for both passengers. Seatless/dummy parts should omit it.

The approved September 2026 tuning is authored in 279 ride objects / 336 passenger-car definitions, using 1, 1.5, 2,
2.5 or 3 seconds according to seating geometry and restraints. All kart variants use 2 seconds. These compressed gameplay
values are not measured real-world boarding or safety-check times.

The engine companion repository documents the full per-family mapping, exceptions and research rationale in
`docs/vehicle-boarding-duration-rationale.md`, and the parser/runtime/save contract in `docs/guest-services-and-boarding.md`.
Existing artwork and image references are unaffected by this property.
