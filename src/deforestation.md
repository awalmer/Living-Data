---
toc: true
header: "Biodiversity >> Deforestation"
style: custom-style.css
---

```js
const trees_mapping = FileAttachment("data/global-forest-area-display-mapping.csv").csv({typed: true});
```

```js
const treesDisplayMapping = trees_mapping.map(d => ({
  Year: String(d.Year ?? d.year ?? d["Year"]), // handles commas
  "Forest Area (K ha)": d["Forest Area (K ha)"],
  "MIDI Notes": d["MIDI Notes"],
  "Amplitude": d["Amplitude"]
}));
```

```js
const tree_photo_1 = FileAttachment("photos/deforestation-logic-screenshot-1.jpeg").image({alt: "Logic Session, Deforestation"})
// control width with:
// ...FileAttachment("photos/deforestation-logic-screenshot-1.jpeg").image({width: 900, alt: "Logic Session, Deforestation"})
const tree_photo_2 = FileAttachment("photos/deforestation-logic-screenshot-2.jpeg").image({alt: "Logic Session, Deforestation"})
```

<h2>Design Approach</h2>
<ol style="font-size: 110%;">
    <li>Use sounds that are akin to "wood" → e.g. wooden mallets, resonant drums, natural materials...</li>
    <br>
    <li>As global forest area decreases...</li>
        <ul>
            <li>...number of notes decreases</li>
            <li>...amplitude decreases</li>
        </ul>
    <br>
    <li>Soundscape of tropical rainforest</li>
</ol>

<div class="card card-fit-content">${tree_photo_2}</div>

<br>
<br>

<h2>Mapping</h2>
<ul style="font-size: 110%;">
    <li>Number of MIDI Notes: 30 to 5</li>
    <li>Amplitude: 0 dB to -12 dB</li>
    <li>Decade Marker: tree falling</li>
</ul>
<div class="card card-fit-content">
    ${Inputs.table(treesDisplayMapping)}
</div>

<br>

<div class="card card-fit-content">${tree_photo_1}</div>



<!-- 
<div class="grid grid-cols-2 wide-v" style="grid-auto-rows: auto;">
  <div class="card">${tree_photo_2}</div>
  <div class="card">It is a way I have of driving off the spleen and regulating the circulation.</div>
</div>
-->






<style>
  /* Target the Inputs.table inside this card */
  .card table {
    width: auto !important;           /* Don’t stretch to container */
    table-layout: auto !important;    /* Let columns size naturally */
  }
  .card th, .card td {
    white-space: nowrap;              /* Prevent line breaks */
    padding-right: 12px;              /* Add a bit of spacing */
    font-size: 130%;
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
        min-width: 80%;
        padding: 0 1rem; /* optional */
        margin: 0 auto;
    }
</style>