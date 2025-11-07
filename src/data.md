---
toc: true
header: "Prelude >> Data"
style: custom-style.css
---

```js
const biomass = FileAttachment("data/biomass-mammals-display.csv").csv({typed: true});
const biomass_data = FileAttachment("data/biomass-mammals.csv").csv({typed: true});
// const trees = FileAttachment("data/deforestation-display.csv").csv({typed: true});
const trees = FileAttachment("data/global-forest-area-display.csv").csv({typed: true});
const whales = FileAttachment("data/whales-display.csv").csv({typed: true});
```

```js
const treesDisplay = trees.map(d => ({
  Year: String(d.Year ?? d.year ?? d["Year"]), // handles commas
  "Forest Area (K ha)": d["Forest Area (K ha)"],
  // "Wooded Land (K ha)": d["Wooded Land (K ha)"]
}));
```

```js
import * as Plot from "npm:@observablehq/plot";

const biomass_chart = Plot.plot({
  title: "The long-run decline of the world's wild mammals",
  caption: "Chart is modeled after published version from Our World in Data.",
  width: 700, // smaller overall size
  height: 250,
  marginTop: 40, // ↑ space above chart
  marginLeft: 50,
  marginBottom: 40,
  x: {
    label: "Year",    // categorical x-axis
    tickRotate: 0,
    tickFormat: String,
    labelOffset: 30
  },
  y: {
    label: "Biomass (million tons of carbon)",
    grid: true
  },
  style: {
    fontSize: "14px",      // ← global font size
    fontFamily: "sans-serif",
    background: "transparent" // optional: blend better in cards
  },
  color: {
    legend: false
  },
  marks: [
    Plot.barY(biomass_data, {
      x: "Year",
      y: "Biomass_mil_carbon",
      fill: "orange",
      tip: true, // built-in tooltip
      sort: {x: "-y"} // sort chronologically
    }),
    Plot.ruleY([0])
  ]
});
```

```js
import * as Plot from "npm:@observablehq/plot";

const deforestation_chart = Plot.plot({
  title: "Reduction in Global Forest Area, 1990-2025",
  caption: "Data is derived from the Global Forest Resource Assessment (2025).",
  width: 700,
  height: 300,
  marginLeft: 90, 
  marginBottom: 50,
  x: {label: "Year", tickFormat: String},
  y: {
    label: "Forest Area (K ha)",
    // Fit y-axis to the min/max of data
    domain: [
      Math.min(...trees.map(d => d["Forest Area (K ha)"])) * 0.995, 
      Math.max(...trees.map(d => d["Forest Area (K ha)"])) * 1.005
    ],
    grid: true
  },
  style: {fontFamily: "sans-serif", fontSize: "14px"},
  marks: [
    Plot.lineY(trees, {x: "Year", y: "Forest Area (K ha)", stroke: "forestgreen", strokeWidth: 3, curve: "catmull-rom", tip: true}),
    Plot.dot(trees, {x: "Year", y: "Forest Area (K ha)", fill: "forestgreen"})
  ]
});
```

<h2>Biodiversity — <em>Decline of Wild Mammals</em></h2>
<p><a href="https://ourworldindata.org/biodiversity?insight=wild-mammals-have-declined-by-85-since-the-rise-of-humans#key-insights" target="_blank">Our World in Data</a></p>


<div class="grid grid-cols-2">
    <div>
        <p>Wild mammals have declined by 85% since the rise of humans, based on estimates of the total biomass of the world's wild land mammals. Biomass provides a proxy for the richness of the mammal kingdom.</p>
    </div>
    <div class="card card-fit-content" style="padding: 6px;">
        ${Inputs.table(biomass)}
    </div>
</div>

<div class="card card-fit-content" style="padding: 20px;">
    ${biomass_chart} 
</div>


<br>
<br>

<h2>Biodiversity — <em>Deforestation</em></h2>
<p><a href="https://openknowledge.fao.org/server/api/core/bitstreams/2dee6e93-1988-4659-aa89-30dd20b43b15/content/cd6709en.html" target="_blank">Global Forest Resource Assessment (2025)</a></p>
<div class="grid grid-cols-2">
    <div>
        <p>Key Findings:
            <ul>
                <li>The world is losing more forest than it gains every year.</li>
                <li>However! Rates of deforestation are declining around the world since 1990. 👏 </li>
                <li>Driving Factors: "Agriculture has historically been the leading cause of forest loss, but wildfire is increasingly posing a threat. Wildfires were the leading driver of tropical forest loss in 2024 for the first time on record." (UN report)</li>
            </ul>
        </p>
    </div>
    <div class="card card-fit-content">
        ${Inputs.table(treesDisplay)}
    </div>
</div>
<div class="card card-fit-content" style="padding: 20px;">
    ${deforestation_chart}
</div>

<br>
<br>

<h2>Biodiversity — <em>Whale Population Devastation</em></h2>
<p><a href="https://ourworldindata.org/biodiversity?insight=wild-mammals-have-declined-by-85-since-the-rise-of-humans#key-insights" target="_blank">Our World in Data</a></p>

<div class="grid grid-cols-2">
    <div>
    <ul>
      <li>The 'modern' whaling era spanned from 1890 onwards.</li>
      <li>At its peak in the 1960s, we were hunting 80,000 whales every year, and whale populations were become increasingly depleted.</li>
      <li>1987: The International Whaling Commission (IWC) agreed on a moratorium.</li>
    </ul>
    </div>
    <div class="card card-fit-content">
        ${Inputs.table(whales)}
    </div>
</div>

<div class="card">
    <iframe src="https://ourworldindata.org/grapher/whale-populations?tab=chart" loading="lazy" style="width: 100%; height: 500px; border: 0px none;" allow="web-share; clipboard-write"></iframe>
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
    font-size: 120%;
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

    /* Full width option ~ 85% */
    main, main article, .content {
        max-width: 100%;
        min-width: 70%;
        padding: 0 1rem; /* optional */
        margin: 0 auto;
    }
</style>