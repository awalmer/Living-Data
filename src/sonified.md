---
toc: true
header: "Poetry >> Spoken"
style: custom-style.css
---

```js
const praat1 = FileAttachment("photos/poetry-praat-1.jpg").image({alt: "Praat"})
const praat2 = FileAttachment("photos/poetry-praat-2.jpg").image({alt: "Praat"})
const midimap = FileAttachment("photos/poetry-midi-map.jpg").image({alt: "MIDI Map"})
const freq1 = FileAttachment("photos/poetry-logic-freq-1.jpg").image({alt: "Logic Session"})
const freq2 = FileAttachment("photos/poetry-logic-freq-2.jpg").image({alt: "Logic Session"})
```


<h2>Design Approach</h2>
<ol style="font-size: 110%;">
    <li>Subjective, interpretive textual analysis (+ some NLP).</li>
    <li>Encoding audio to data >> and data to sound.</li>
</ol>

<!-- <div class="card card-fit-content"></div> -->

<div class="grid grid-cols-2" style="grid-auto-rows: auto;">
  <div class="card card-fit-content">${praat1}</div>
  <div class="card card-fit-content">${praat2}</div>
</div>

<div class="grid grid-cols-2" style="grid-auto-rows: auto;">
  <div class="card card-fit-content">${midimap}</div>
  <div class="card card-fit-content">${freq2}</div>
</div>

<div class="card card-fit-content">${freq1}</div>



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