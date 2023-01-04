<script>
  // Logic goes here (JavaScript, Svelte)
  import data from '$data/data.js';
  import { scaleLinear } from 'd3-scale';
  import { max } from 'd3-array';
  import AxisX from '$components/AxisX.svelte';
  let width = 400;
  let height = 400;
  let xScale = scaleLinear().domain([0, 100]).range([0, width]);
  let yScale = scaleLinear()
    .domain([0, max(data, (d) => d.hours)])
    .range([height, 0]);
  // console.log(data);
</script>

<main>
  <!-- Markup goes here (HTML, SVG) -->
  <svg {width} {height}>
    <AxisX {height} {xScale} />
    {#each data as d}
      <circle
        cx={xScale(d.grade)}
        cy={yScale(d.hours)}
        r={10}
        fill="cornflowerblue"
        stroke="black"
        stroke-width={1}
      />
    {/each}
  </svg>
</main>

<style>
  /* Styles go here (CSS) */
</style>
