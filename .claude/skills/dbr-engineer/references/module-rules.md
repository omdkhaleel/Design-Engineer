# Module list & applicability rules

Used in Step 2 of the main workflow to build the DBR Configuration Matrix.

## Core modules (evaluate for every project)

These are normally applicable to any HVAC-scoped project. Only drop one if the project
genuinely has no basis for it (e.g. a pure ventilation-only warehouse might not need a
full indoor-conditions table).

1. Cover Page
2. Project Brief
3. Outdoor Design Conditions
4. Indoor Design Conditions
5. Heat Load Design Consideration
6. Heat Load Summary
7. Codes & Standards

## Dynamic modules (applicable only if triggered)

8. Process Load Design Consideration
9. Process Load Summary
10. Chiller Plant Proposal / Configuration
11. Process Plant Proposal / Configuration (PCW)
12. HVAC System Description
13. PCW System Description
14. Ventilation & Exhaust
15. Cleanroom / Controlled Environment
16. Heating System
17. Humidification / Dehumidification
18. Redundancy & Reliability
19. Controls & BMS
20. Energy Efficiency
21. Water Consumption
22. Equipment Selection
23. Engineering Calculations
24. Equipment Schedule
25. Design Assumption Register
26. Data Gap Register
27. Engineering Decision Log
28. Design Review Comments
29. Appendices

## Applicability rules

Apply this logic when building the matrix. These are triggers, not guarantees — use
judgment on borderline cases and mark them "To Be Confirmed" rather than forcing a
yes/no.

| If... | Then... |
|---|---|
| General HVAC exists | HVAC System Description = Applicable |
| Process exists | Process Load Design = Applicable |
| Process generates heat | Process Load Summary = Applicable |
| Process cooling exists | Process Plant = Applicable |
| Process cooling uses water | PCW = Applicable |
| Chilled water is required | Chiller Plant = Applicable |
| Cooling towers are required | Cooling tower info folded into Chiller/Process Plant section (no separate section) |
| Cleanroom exists | Cleanroom = Applicable |
| Significant exhaust exists | Ventilation & Exhaust = Applicable |
| Heating exists | Heating System = Applicable |
| Humidity control is required | Humidification/Dehumidification = Applicable |
| 24×7 or mission-critical operation | Redundancy = Applicable |
| BMS exists | Controls & BMS = Applicable |
| Significant energy consumption or sustainability target | Energy Efficiency = Applicable |
| Cooling towers exist | Water Consumption = Applicable |
| Equipment selection is part of the current design stage | Equipment Selection = Applicable |
| Sufficient engineering data exists | Engineering Calculations = Applicable |
| Assumptions exist | Design Assumption Register = Applicable |
| Critical data is missing | Data Gap Register = Applicable |
| Major alternatives were evaluated | Engineering Decision Log = Applicable |

The final DBR must not show sections marked Not Applicable — don't include a
placeholder or an "N/A" row, just leave the section out entirely.

## Configuration matrix format

Present this as a table with these columns:

`Module | Applicability | Trigger | Reason | Inputs Required | Status`

Example rows:

```
Process Load        | Applicable     | Process equipment present | Heat rejection data available | Equipment data          | Confirmed
PCW                  | Applicable     | Process cooling water required | PCW requirement stated   | Vendor data             | Preliminary
Cleanroom             | Not Applicable | No cleanroom specified     | —                              | —                       | Closed
Chiller Plant         | Applicable     | Central CHW required       | Cooling load driving plant sizing | Load calculation | Preliminary
```

## Project classification categories

Use these as a starting vocabulary, not an exhaustive or exclusive list — a project
can span more than one:

Commercial, Office, IT, Data Centre, Hospital, Hotel, Residential, Retail, Airport,
Railway/Metro, Warehouse, Manufacturing, Industrial, Pharmaceutical, Cleanroom,
Semiconductor, Solar Manufacturing, Battery Manufacturing, Automotive, Food
Processing, Chemical, Laboratory, Power Plant, Utility Plant, Infrastructure,
Mixed-use, Other.

Classify from what the user actually told you about the project — don't infer a
specialized process requirement (e.g. cleanroom, PCW) just because a project *name*
sounds industrial. A "solar manufacturing facility" doesn't automatically imply
cleanroom HVAC until the process description confirms it.
