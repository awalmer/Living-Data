---
toc: true
header: "Biodiversity >> Biomass"
style: custom-style.css
---

```js
const biomass1 = FileAttachment("photos/biomass-audio-samples.jpg").image({alt: "Biomass"})
const biomass2 = FileAttachment("photos/biomass-layers.jpg").image({alt: "Biomass"})
const biomass3 = FileAttachment("photos/biomass-samples.jpg").image({alt: "Biomass"})
const biomass4 = FileAttachment("photos/biomass-randomize-1.jpg").image({alt: "Biomass"})
const biomass5 = FileAttachment("photos/biomass-randomize-2.jpg").image({alt: "Biomass"})
const biomass6 = FileAttachment("photos/biomass-randomize-3.jpg").image({alt: "Biomass"})
```

<h2>Design Approach</h2>
<ol style="font-size: 110%;">
    <li>Stack many layers for sonic richness to represent biodiversity.</li>
    <br>
    <li>Download wild mammal audio samples and randomize through time frame. As biodiversity decreases...</li>
        <ul>
            <li>...the number of animal sounds decreases.</li>
            <li>...the number of notes decreases.</li>
            <li>...the range of musical notes decreases.</li>
        </ul>
      <br>
    <li>Constrain to D Dorian scale.</li>
</ol>

<h2>Mapping</h2>
<ul style="font-size: 110%;">
    <li>100K Years Ago: 40 MIDI notes, 40 audio samples of animals, 10 layers of chord</li>
    <li>10K Years Ago: 30 MIDI notes, 30 audio samples of animals, 7 layers of chord</li>
    <li>125 Years Ago: 20 MIDI notes, 20 audio samples of animals, 5 layers of chord</li>
    <li>Today: 6 MIDI notes, 6 audio samples of animals, 1 layers of chord</li>
</ul>


<br>

<div class="grid grid-cols-2" style="grid-auto-rows: auto;">
  <div class="card card-fit-content">${biomass1}</div>
  <div class="card card-fit-content">${biomass2}</div>
  <div class="card card-fit-content">${biomass3}</div>
  <div class="card card-fit-content">${biomass4}</div>
  <div class="card card-fit-content">${biomass5}</div>
  <div class="card card-fit-content">${biomass6}</div>
</div>

<div class="card card-fit-content"></div>



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
        min-width: 95%;
        padding: 0 1rem; /* optional */
        margin: 0 auto;
    }
</style>