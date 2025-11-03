---
toc: true
header: "Prelude >> Data"
style: custom-style.css
---

```js
const biomass = FileAttachment("data/biomass-mammals-display.csv").csv({typed: true});
const trees = FileAttachment("data/deforestation-display.csv").csv({typed: true});
const whales = FileAttachment("data/whales-display.csv").csv({typed: true});
```
```js
const treesDisplay = trees.map(d => ({
  Year: String(d.Year ?? d.year ?? d["Year"]), // handles commas
  "Forest Area (K ha)": d["Forest Area (K ha)"],
  "Wooded Land (K ha)": d["Wooded Land (K ha)"]
}));
```

<h2>Biodiversity — <em>Decline of Wild Mammals</em></h2>
<p><a href="https://ourworldindata.org/biodiversity?insight=wild-mammals-have-declined-by-85-since-the-rise-of-humans#key-insights" target="_blank">Our World in Data</a></p>


<div class="grid grid-cols-2">
    <div>
        <p>Et malesuada fames ac turpis. Integer vitae justo eget magna fermentum iaculis eu non diam. Aliquet risus feugiat in ante metus dictum at. Consectetur purus ut faucibus pulvinar.</p>
    </div>
    <div class="card card-fit-content" style="padding: 6px;">
        ${Inputs.table(biomass)}
    </div>
</div>

<br>

<h2>Biodiversity — <em>Deforestation</em></h2>
<p><a href="https://www.sciencedirect.com/science/article/pii/S0378112715003400" target="_blank">"Dynamics of Global Forest Area" (2015)</a></p>
<div class="grid grid-cols-2">
    <div>
        <p>Findings from Global Forest Resources Assessment 2015 (FRA 2015).
            <ul>
                <li>Global forest area decreased by 3% from 1990 (4128 M ha) to 2015 (3999 M ha).</li>
                <li>CHANGE DATA? https://www.carbonbrief.org/un-report-five-charts-showing-how-global-deforestation-is-declining/ </li>
                <li>The rate of net forest loss was greater in the 1990s</li>
                <li>Grape</li>
            </ul>
        </p>
    </div>
    <div class="card card-fit-content">
        ${Inputs.table(treesDisplay)}
    </div>
</div>

<br>

<h2>Biodiversity — <em>Whale Population Devastation</em></h2>
<p><a href="https://ourworldindata.org/biodiversity?insight=wild-mammals-have-declined-by-85-since-the-rise-of-humans#key-insights" target="_blank">Our World in Data</a></p>

<div class="grid grid-cols-2">
    <div>
        <p>Et malesuada fames ac turpis. Integer vitae justo eget magna fermentum iaculis eu non diam. Aliquet risus feugiat in ante metus dictum at. Consectetur purus ut faucibus pulvinar.</p>
    </div>
    <div class="card card-fit-content">
        ${Inputs.table(whales)}
    </div>
</div>

<br>

<hr> <!-- horizontal line break -->

<h2>Poetry — <em>"Invitation"</em> by Mary Oliver</h2>

<p>
<br>
Oh do you have time<br>
to linger<br>
for just a little while<br>
out of your busy<br>

and very important day<br>
for the goldfinches<br>
that have gathered<br>
in a field of thistles<br>

for a musical battle,<br>
to see who can sing<br>
the highest note,<br>
or the lowest,<br>

or the most expressive of mirth,<br>
or the most tender?<br>
Their strong, blunt beaks<br>
drink the air<br>

as they strive<br>
melodiously<br>
not for your sake<br>
and not for mine<br>

and not for the sake of winning<br>
but for sheer delight and gratitude — <br>
believe us, they say,<br>
it is a serious thing<br>

just to be alive<br>
on this fresh morning<br>
in the broken world.<br>
I beg of you,<br>

do not walk by<br>
without pausing<br>
to attend to this<br>
rather ridiculous performance.<br>

It could mean something.<br>
It could mean everything.<br>
It could be what Rilke meant, when he wrote:<br>
You must change your life.
</p>


<style>
  /* Target the Inputs.table inside this card */
  .card table {
    width: auto !important;           /* Don’t stretch to container */
    table-layout: auto !important;    /* Let columns size naturally */
  }
  .card th, .card td {
    white-space: nowrap;              /* Prevent line breaks */
    padding-right: 12px;              /* Add a bit of spacing */
  }
  .card-fit-content {
    padding: 6px;
    display: inline-block;
    width: fit-content;
  }
  
  /* FIX FOR TABLE BEING TALLER THAN NEEDED: */
    .grid {
    align-items: start; /* Prevents equal-height stretching */
    }
</style>