---
title: Breath Types
weight: 5
---

## Breath types during mechanical ventilation
### Continous mandatory ventilation
In this mode, all breaths are mandatory, and depend soley on the ventilatory settins. They can be either volume-controlled, or pressure controlled.

### Continous supportive ventilation
All breaths are spontanious

### Intermittent mandatory ventilation
Both spontaneious and mandatory breaths are delivered.

### Deducing ventilation mode vased on breath type

<div class="mermaid">
graph TD
    Mandatory[Are mandatory breaths allowed?]
    Spont[Are spontaneous breath allowed between mandatory breaths?]
    Mandatory -- No --> CSV
    Mandatory -- Yes --> Spont
    Spont -- No --> CMV
    Spont -- Yes --> IMV
</div>
