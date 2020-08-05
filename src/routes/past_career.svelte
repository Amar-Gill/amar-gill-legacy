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
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDY0jTO8ynyAIUFfDSB4G5U8HHKB6SXSns&callback=initMap">

  </script>
</svelte:head>

{#if mapLoaded}
  <Map />
{/if}
