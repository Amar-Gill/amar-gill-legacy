<script>
  import Map from "../components/Map.svelte";

  let mapLoaded = false;

  if (process.browser === true) {
    window.initMap = () => {
      mapLoaded = true;
    };
  }
</script>

<svelte:head>
  <title>Map of Past Career Projects</title>
  <script
    defer
    async
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDPglwdDlv5LhkGGQPIDkz2uTBqM35eh0M&callback=initMap">

  </script>
</svelte:head>

{#if mapLoaded}
  <Map />
{/if}
