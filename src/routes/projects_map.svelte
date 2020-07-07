<svelte:head>
    <title>Interactive Resume</title>
    <script defer async
        src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDPglwdDlv5LhkGGQPIDkz2uTBqM35eh0M&callback=initMap">
        </script>
</svelte:head>



<script>
    import mapStyles from '../../static/map-styles'; // optional
    import Menu from '../components/Menu.svelte';

    let activeProject;

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
    let beProjects = [
        {
            title: "Humber NX",
            center: { lat: 43.728515, lng: -79.607363 }
        },
        {
            title: "Novus",
            center: { lat: 43.639053, lng: -79.409972 }
        },
        {
            title: "Niagara Falls Entertainment Complex",
            center: { lat: 43.082821, lng: -79.083895 }
        }
    ]

    let energyProjects = [
        {
            title: "Domestic Waterline Replacement",
            center: { lat: 44, lng: -76 }
        },
        {
            title: "Cheakamus Generator Replacement",
            center: { lat: 30, lng: -80 }
        },
        {
            title: "Diablo Canyon Generator Replacement",
            center: { lat: 31, lng: -72 }
        }
    ]

    let sustainabilityProjects = [
        {
            title: "lit vibes",
            center: { lat: 41.1, lng: -80.7 }
        },
        {
            title: "chill vibes",
            center: { lat: 39.9, lng: -80.4 }
        },
        {
            title: "It's wavy",
            center: { lat: 33.3, lng: -77.7 }
        }
    ]

</script>

<div class="full-screen" bind:this={container}>
</div>

{#if map}
<Menu {sustainabilityProjects} {energyProjects} {beProjects} {map}
 on:select="{(event) => activeProject=event.detail.project}" />
{/if}

{#if activeProject}
<aside  >WAGWAN G?
    {activeProject.title}
</aside>
{/if}

<style>
    .full-screen {
        width: 100vw;
        height: calc(100vh - 5.5rem);
    }

    aside {
        position: fixed;
        top: 9%;
        right: 2%;
    }
</style>