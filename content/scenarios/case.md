---
title: Clinical Case
weight: 5
---

A 22 year old female with history of asthma was admitted to the ED with shortness of breath. Her dyspnea worsened, and she failed to respond to non-invasive therapy. She was ultimately intbuated.

The initial ventilation settings were: <u> mode AC/VC, tidal volume 500 ml, respiratory rate 22 per min,
PEEP 5 mmHg, Flow 60 L per min. </u>

You were called to her bedside as she has been getting progressivly more hypotensive over the past 30 minutes.

Take a look at the vent monitor below, and make appropriate changes to the vent. You can use the <b>Pause Flow</b> button below to pause the flow, and assess alveolar pressure. 

As you change the settings watch the total PEEP, and retained volume change. The goal is to decrease the two numbers as much as possible. 


#### OPTION 1 - Adjust the Tidal Volume

<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.TV = 800">Increase TV to 800 ml</button>
<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.TV = 300">Decrease TV to 300 ml</button>
<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.TV = 100">Decrease TV to 100 ml</button>

#### OPTION 2 - Adjust the Respiratory Rate</h5>

<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.RR = 30">Increase RR to 30 breath per min</button>
<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.RR = 15">Decrease RR to 15 breath per min</button>
<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.RR = 10">Decrease RR to 10 breath per min</button>

#### OPTION 3 - Change the Amount of Flow</h5>

<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.Flow = 30">Decrease the flow to 30 L/min</button>
<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.Flow = 60">Keep the flow at 60 L/min</button>
<button class="btn-small btn-flat deep-purple lighten-4" onclick="Vent.Flow = 90">Increase the flow to 90 L/min</button>

<div id="p5canvas"></div>

<div>
    <!-- Play Controls -->
    <button class="btn-small btn-flat yellow lighten-4" onclick="Controls.pauseResume()">Pause | Resume</button>
    <button class="btn-small btn-flat green lighten-4" onclick="Graph.clear()">Clear</button>
    <!-- Zoom Controls -->
    <button class="btn-small btn-flat light-blue lighten-4" onclick="Controls.xplus()">X+</button>
    <button class="btn-small btn-flat light-blue lighten-4" onclick="Controls.xminus()">X-</button>
    <button class="btn-small btn-flat light-blue lighten-4" onclick="Controls.yplus()">Y+</button>
    <button class="btn-small btn-flat light-blue lighten-4" onclick="Controls.yminus()">Y-</button>
    <!-- Toggle Controls -->
    <button class="btn-small btn-flat deep-purple lighten-4" onclick="Controls.togglePalv()">Palv</button>
    <button class="btn-small btn-flat deep-purple lighten-4" onclick="Controls.togglePmus()">Pmus</button>
    <!-- Flow Pause Controls -->
    <button class="btn-small btn-flat red lighten-4" ontouchstart="Controls.holdFlowInsp()" ontouchend="Controls.releaseFlow()" onmouseup="Controls.releaseFlow()" onmousedown="Controls.holdFlowInsp()">Insp Pause</button>
    <button class="btn-small btn-flat red lighten-4" ontouchstart="Controls.holdFlowExp()" ontouchend="Controls.releaseFlow()" onmouseup="Controls.releaseFlow()" onmousedown="Controls.holdFlowExp()">Exp Pause</button>
 <div id="lastcycle">
    <p><u>Pertinent Metrics:</u>
        Peak Pressure: {{Math.round(maxPaw)}} cmH2O, Plateau Pressure: {{Math.round(maxPalv)}} cmH2O,
        <b>Total PEEP: </b>{{Math.round(minPalv)}} cmH2O,
        <b>Retained Volume: </b>{{Math.round(minVolume * 1000)}}
        mL.
    </p>
</div>

</div>



<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/p5.min.js"></script>
<script src="https://iculearning.com/api/main.bundle.js"></script>

<script type="text/javascript">
    Vent.RR = 25;
    Lung.Resistance = 30;
    window.onload = function () {
        Controls.xplus();
        Controls.xplus();
        Controls.xplus();
        Controls.yminus();
        Controls.yminus();
    }
</script>
