---
toc: true
header: "Prelude >> Data"
style: custom-style.css
---

```js
const biomass = FileAttachment("data/biomass-mammals-display.csv").csv({typed: true});
```

<h2>Biodiversity — <em>Decline of Wild Mammals</em></h2>
<h3>Our World in Data</h3>


<div class="grid grid-cols-2">
    <div>
        <p>Et malesuada fames ac turpis. Integer vitae justo eget magna fermentum iaculis eu non diam. Aliquet risus feugiat in ante metus dictum at. Consectetur purus ut faucibus pulvinar.</p>
    </div>
    <div class="card" style="padding: 6px; width: 70%; display: flex;">
        ${Inputs.table(biomass)}
    </div>
</div>

<br>

<h2>Biodiversity — <em>Deforestation</em></h2>
<div class="grid grid-cols-2">
    <div>
        <p>Et malesuada fames ac turpis. Integer vitae justo eget magna fermentum iaculis eu non diam. Aliquet risus feugiat in ante metus dictum at. Consectetur purus ut faucibus pulvinar.</p>
    </div>
    <div class="card" style="padding: 6px;">
        ${Inputs.table(biomass)}
    </div>
</div>

<br>

<h2>Biodiversity — <em>Whale Population Devastation</em></h2>
<h3>Our World in Data</h3>
<div class="grid grid-cols-2">
    <div>
        <p>Et malesuada fames ac turpis. Integer vitae justo eget magna fermentum iaculis eu non diam. Aliquet risus feugiat in ante metus dictum at. Consectetur purus ut faucibus pulvinar.</p>
    </div>
    <div class="card" style="padding: 6px;">
        ${Inputs.table(biomass)}
    </div>
</div>

<br>

<h2>Poetry — <em>"Invitation"</em> by Mary Oliver</h2>
