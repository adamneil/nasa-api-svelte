<script>
  import { onMount } from "svelte";

  let pod;

  onMount(async () => {
    const res = await fetch(
      "https://api.nasa.gov/planetary/apod?api_key=Y2iexOoVessNH8V3BpMfzK1FErpeIGG6j5TGsOdh"
    );
    pod = await res.json();
    console.log(pod);
  });
</script>

<style>
  .container {
    display: grid | inline-grid;
  }
</style>

{#if pod}
  <div class="container">
    <h1>{pod.explanation}</h1>
    <img src={pod.url} alt="" />
  </div>
{/if}
