<svelte:head>
    <script defer async
        src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDPglwdDlv5LhkGGQPIDkz2uTBqM35eh0M&callback=initMap">
        </script>
</svelte:head>



<script>
    import mapStyles from '../../static/map-styles'; // optional
    import Menu from '../components/Menu.svelte';

    let map;
    let container;
    let zoom = 11;
    let center = {
        lat: 43.750,
        lng: -79.383
    };

    window.initMap = () => {
        map = new google.maps.Map(container, {
            center,
            zoom,
            styles: mapStyles, // optional
            mapTypeControl: false,
            fullscreenControl: false,
            streetViewControl: false
        });
    }

</script>

<div class="full-screen" bind:this={container}>
</div>
{#if map}
<Menu map={map}/>
{/if}


<style>
    .full-screen {
        width: 100vw;
        height: calc(100vh - 3.6rem);
    }
</style>