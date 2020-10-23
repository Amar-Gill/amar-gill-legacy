<script>
  import Map from "../components/Map.svelte";
  import {goto} from "@sapper/app";

  let mapLoaded = false;

  if (process.browser === true) {
    window.initMap = () => {
      mapLoaded = true;
    };
  }
</script>

<style>
  button {
    position: fixed;
    left: 1%;
    top: 3%;
    z-index: 2;
    background-color: rgba(0,0,0,0.85);
    border-radius: 9px;
    color: var(--text);
    font-size: 1.25rem;
  }
  
</style>

<svelte:head>
  <title>Map of Past Career Projects</title>
  <script
    defer
    async
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDPglwdDlv5LhkGGQPIDkz2uTBqM35eh0M&callback=initMap">

  </script>
</svelte:head>

<button on:click={() => goto("/")}>&#8592;</button>

{#if mapLoaded}
  <Map />
{/if}
