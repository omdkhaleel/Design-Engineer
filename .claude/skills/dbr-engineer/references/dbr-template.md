# DBR structure, table formats, and validation checklist

Used in Step 5 (writing) and Step 6 (validating) of the main workflow. Include only
the sections your Configuration Matrix marked Applicable — this is a menu, not a
mandatory checklist.

## Document shell

**Cover Page:** Project Name, Project Location, Client, Consultant, Document Title,
Document Number, Revision, Date, Prepared By, Checked By, Approved By.

**Document Control:** the same header fields plus a Revision History table —
Revision / Date / Description / Prepared / Checked / Approved.

## Section structure (numbered 1–23, include only applicable ones)

1. **Project Brief** — overview, objective, location, building/facility, area,
   occupancy, operating schedule, process, HVAC scope, process cooling scope, major
   design considerations.

2. **Outdoor Design Conditions** — table of `Parameter | Value | Unit | Source/Basis |
   Status`. Include as applicable: DB, WB, RH, dew point, winter DB, monsoon, pressure,
   altitude, solar radiation, wind speed. Cite the climatic data source and its
   date/version — never fabricate a design-condition value.

3. **Indoor Design Conditions** — area-wise table: `Area | Temperature | RH | Dew
   Point | Air Changes | Fresh Air | Pressure | Cleanliness | Occupancy | Operating
   Hours | Remarks`.

4. **Heat Load Design Consideration** — walk through what's actually contributing to
   the load for this project (don't list factors that don't apply): envelope, roof,
   walls, glass, solar, people, lighting, equipment, electrical, IT, motors, pumps,
   fans, process, fresh air, infiltration, exhaust replacement, ventilation, fan heat,
   pump heat. Keep sensible, latent, ventilation, and process loads separated — don't
   merge them into one number the reader can't decompose.

5. **Heat Load Summary** — table: `Area | Floor Area | Sensible | Latent |
   Ventilation | Process/Internal | Total | Diversity | Design Margin | Design Load |
   TR`. Every number here should trace back to section 4.

6. **Process Load Design Consideration** *(if applicable)* — process, equipment, heat
   rejection, cooling, heating, exhaust, moisture, operating schedule, diversity,
   simultaneity.

7. **Process Load Summary** *(if applicable)* — table: `Equipment | Quantity |
   Connected Load | Operating Load | Diversified Load | Cooling Load | Cooling Medium |
   Flow | Supply | Return | Criticality`.

8. **Chiller Plant Proposal / Configuration** *(if applicable)* — compare air-cooled
   vs. water-cooled, screw vs. centrifugal, etc. where more than one option is
   credible; state capacity, quantity, duty/standby split, CHW supply/return, flow,
   pumps, cooling towers, heat rejection, future-expansion provision. Choose N / N+1 /
   N+2 / 2N redundancy based on the project's actual criticality, not by default.

9. **Process Plant Proposal / Configuration (PCW)** *(if applicable)* — PCW/CHW
   architecture, heat exchangers, pumps, cooling towers, filtration, water treatment,
   buffer/expansion tanks, chemical dosing, controls. Compare alternative
   configurations where more than one is credible.

10. **HVAC System Description** *(if applicable)* — system selection (AHU / FAHU /
    MAU / PAHU / FCU / VRF / DX / package / rooftop / FFU / HEPA / dedicated process
    HVAC) reasoned from building type, load, operating hours, temperature/RH, fresh
    air, process, criticality, energy — not picked by convention alone.

11. **PCW System Description** *(if applicable)* — supply/return temperatures, flow,
    pressure, pumps, heat exchangers, chillers, cooling towers, filtration, water
    treatment, expansion, distribution, controls, redundancy.

12. **Ventilation & Exhaust** *(if applicable)* — fresh air, general ventilation,
    process/chemical/heat/dust/lab exhaust, make-up air, fans, filtration, scrubbing,
    pressure relationships.

13. **Cleanroom / Controlled Environment** *(if applicable)* — ISO classification,
    temperature, RH, ACH, airflow pattern, FFU, HEPA, pressure cascade, return air,
    airlocks, gowning, contamination control.

14. **Heating / Humidification / Dehumidification** *(if applicable)*.

15. **Redundancy & Reliability** *(if applicable)* — reasoned from criticality,
    failure consequence, operating hours, recovery time, maintenance access, client
    requirement. Don't default to N+1 everywhere.

16. **Controls & BMS** *(if applicable)* — temperature/RH/pressure/flow control,
    chiller and pump sequencing, cooling tower sequencing, lead/lag, standby
    changeover, alarms, interlocks, energy monitoring.

17. **Energy & Water Considerations** *(if applicable)* — chiller/pump/fan efficiency,
    VFDs, variable flow, temperature reset, heat recovery, free cooling, cooling-tower
    consumption, evaporation, blowdown, water treatment.

18. **Equipment Selection** *(if applicable)* — see Equipment Schedule format below.

19. **Engineering Calculations** *(if applicable)* — see Calculation format below.

20. **Design Assumption Register** *(if applicable)* — every ASSUMED item from Step 3
    of the workflow, with basis, impact, confirmation status.

21. **Data Gap Register** *(if applicable)* — every CRITICAL MISSING / TO BE VERIFIED
    item, with priority and who needs to supply it.

22. **Engineering Decision Log** *(if applicable)* — alternatives considered,
    comparison basis, recommendation, and why.

23. **Design Review Comments** *(if applicable)*.

**Appendices** *(if applicable)*.

## Equipment schedule format

`Tag | Description | Quantity | Duty | Standby | Capacity | Flow | Temperature |
Pressure | Motor | Efficiency | Control | Selection Basis`

## Engineering calculation format

Every calculation block needs: Formula, Inputs, Units, Assumptions, Calculation,
Result, Engineering check. Don't skip the "engineering check" line — a sanity check
(e.g. "TR per m² falls within typical range for this building type") is what makes a
number trustworthy rather than just arithmetic.

Prefer a validated external calculation engine/tool over free-form derivation when one
is available and connected. If an external result conflicts with a preliminary
AI-derived number, don't silently overwrite either one — flag the discrepancy, name
the source of each, and ask for engineering confirmation if it matters.

## Codes & standards table format

`Standard | Description | Applicability | Design Area | Status | Remarks`

Draw from what's actually relevant to the project: NBC, IS, ISHRAE, ASHRAE, ISO,
SMACNA, CIBSE, NFPA, IEC, ASME, local regulations, client standards, process
standards. Don't invent clause numbers, and don't claim a standard was "checked"
unless its applicable requirements were actually reviewed against the design.

## Validation checklist (run before issuing)

Heat balance, air balance, water balance, chiller capacity check, PCW capacity check,
cooling tower check, pump check, diversity check, redundancy check, margin check,
indoor-condition check, process-requirement check, standards check. Flag every
inconsistency you find — don't smooth one over to make the report look more finished
than it is.

## Quality bar

Project-specific, technically consistent, traceable, auditable, professional,
client-review ready. Avoid: generic filler, unsupported numbers, hidden assumptions,
contradictory or duplicate loads, duplicate safety factors, invented standards,
irrelevant sections, unnecessary calculations, manufacturer-specific recommendations
unless the user actually asked for them.
