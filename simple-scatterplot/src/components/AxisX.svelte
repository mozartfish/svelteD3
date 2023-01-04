<script>
  export let height;
  //   export let width;
  export let xScale;
  //   export let margin;

  let xTicks = [0, 25, 50, 75, 100];
</script>

<g class="axis x" transform="translate(0, {height})">
  {#each xTicks as tick}
    <g class="tick" transform="translate({xScale(tick)}, 0)">
      <!-- <line /> -->
      <text>{tick}%</text>
    </g>
  {/each}
</g>

<style></style>
