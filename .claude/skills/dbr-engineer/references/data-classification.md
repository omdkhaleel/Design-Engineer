# Data classification, assumptions, minimum inputs, and design-stage depth

## Status labels

Apply one of these to every data point, parameter, and assumption in the DBR so a
reader can tell at a glance how solid it is:

- **CONFIRMED** — from the client/user/vendor, not inferred
- **PRELIMINARY** — a working value, expected to firm up
- **ASSUMED** — filled in by the agent because it wasn't provided and isn't material
  enough to block progress; must carry a basis and impact statement
- **CRITICAL MISSING** — blocks meaningful design; must be asked, not assumed
- **HIGH / MEDIUM / LOW PRIORITY** — for data gaps, how much waiting for it should
  slow things down
- **VENDOR INPUT REQUIRED** — depends on equipment selection not yet made
- **PROCESS INPUT REQUIRED** — depends on process engineering not yet available
- **CLIENT INPUT REQUIRED** — a policy/standard/preference decision only the client
  can make
- **TO BE VERIFIED** — plausible but not independently confirmed

## Assumption engine logic

For every missing input:

1. Would getting this wrong change the design outcome (system type, capacity,
   redundancy, a number a reader would act on)? If yes, it's material.
2. Material → ask the user. Don't proceed on a guess for something like CHW
   supply/return temperature, process heat rejection, criticality, or design stage.
3. Not material → make a preliminary assumption. State:
   - the assumption itself
   - its basis (a standard default, a typical value for this building type, etc.)
   - its impact if wrong (usually small, by definition of "not material")
   - that it needs confirmation before the design stage progresses
4. Never assume a critical parameter silently. If in doubt, treat it as material.

## Minimum project inputs (ask only what applies)

**General:** project name, client, location, project type, design stage, area, number
of buildings, floors, operating hours, occupancy, future expansion.

**Building:** dimensions, orientation, envelope, roof, walls, glass, U-values, shading.

**Climate:** location, summer design condition, winter condition, monsoon condition,
altitude.

**Indoor:** temperature, RH, dew point, air changes, fresh air, pressure,
cleanliness.

**Process (if applicable):** process description, production capacity, equipment,
quantity, heat rejection, cooling requirement, operating profile, simultaneity.

**Chilled water (if applicable):** CHW supply/return temperature, load, chiller
preference, redundancy.

**PCW (if applicable):** supply/return temperature, flow, pressure, heat load, water
quality.

**Special:** cleanroom, GMP, data centre, sustainability targets, client standards,
any special process requirements.

Ask only the subset that's actually missing and actually material — don't run through
this list mechanically as a questionnaire.

## Design-stage depth

The right level of detail depends on what stage the project is at. Producing
detailed-engineering-grade numbers at concept stage is as misleading as leaving tender
documents at concept-level vagueness.

| Stage | What the DBR should contain |
|---|---|
| Concept / Feasibility | Preliminary assumptions, system-level comparisons, order-of-magnitude loads |
| FEED / Basic Engineering | Design criteria, calculated loads, system configuration, preliminary equipment sizing |
| Detailed Engineering | Detailed calculations, firm equipment sizing, hydraulic basis, airside basis, control philosophy |
| Tender | Clear technical requirements, equipment schedules, design criteria sufficient to bid against |
| IFC / As-built | Final, construction-issued values only |

If the user hasn't stated a design stage and it isn't obvious from context, ask — it
changes how much precision is honest to present.
