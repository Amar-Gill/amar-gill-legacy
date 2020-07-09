<svelte:head>
    <title>Interactive Resume</title>
    <script defer async
        src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDPglwdDlv5LhkGGQPIDkz2uTBqM35eh0M&callback=initMap">
        </script>
</svelte:head>

<script>
    import mapStyles from '../../static/map-styles'; // optional
    import Menu from '../components/Menu.svelte';
    import { fly } from 'svelte/transition'

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
            title: "Humber College Building NX",
            center: { lat: 43.728515, lng: -79.607363 },
            role: "Building Envelope Commissioning Agent",
            description: "Construction field review and in situ component testing of windows for the deep energy retrofit of a three storey administrative building on the Humber College North Campus."
        },
        {
            title: "Novus Toronto Foundation Review",
            center: { lat: 43.639053, lng: -79.409972 },
            role: "Field Review Consultant",
            description: "Third party quality assurance review of waterproofing system of a four storey parking garage shared by two high rise residential towers."
        },
        {
            title: "Niagara Falls Entertainment Complex",
            center: { lat: 43.082821, lng: -79.083895 },
            role: "Building Envelope Consultant",
            description: "Construction reviews of building envelope assemblies for a brand new performing arts complex. Assemblies reviewed include curtain wall, cladding and roofing."
        }
    ]

    let energyProjects = [
        {
            title: "Domestic Waterline Replacement",
            center: { lat: 43.870661, lng: -78.724809 },
            role: "Assistant Project Manager",
            description: "Project estimation, risk assessment, planning and oversight of the replacement of the domestic waterline for the Darlington Nuclear Generating Station powerhouse."
        },
        {
            title: "Cheakamus Generator Replacement",
            center: { lat: 49.933698, lng: -123.290886 },
            role: "Project Coordinator",
            description: "Project submittals tracking, labour and materials sourcing, construction planning for the design and installation of new hydroelectric generator at Cheakamus Generating Station."
        },
        {
            title: "Diablo Dam Generator Replacement",
            center: { lat: 48.713850, lng: -121.131345 },
            role: "Project Coordinator",
            description: "Project submittals tracking for the design and installation of the new hydroelectric generator at Diablo Dam Hydropower Station."
        }
    ]

    let sustainabilityProjects = [
        {
            title: "Magna Hall",
            center: { lat: 43.954769, lng: -79.520195 },
            role: "LEED Consultant",
            description: "Administration of the LEED green building standard for the new Magna Hall building at the Seneca College King Campus."
        },
        {
            title: "700 Bay",
            center: { lat: 43.658149, lng: -79.385365 },
            role: "LEED Consultant",
            description: "Administration of the LEED green building standard for a new high rise residential tower."
        },
        {
            title: "The Livmore",
            center: { lat: 43.658417, lng: -79.384403 },
            role: "LEED Consultant",
            description: "Administration of the LEED green building standard for a new high rise residential tower."
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
<aside in:fly="{{x:200, duration: 800}}">
    <p><strong>
        {activeProject.title}
    </strong>
    </p>
    <p><strong>
        Role:
    </strong> {activeProject.role}</p>
    <p><strong>Description:</strong> {activeProject.description}</p>
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
        display: flex;
        flex-direction: column;
        background-color: var(--hue-1);
        border-radius: 9px;
        color: var(--compliment-2);
        box-shadow: .5rem .5rem var(--compliment-1);
        width: 12rem;
        padding: 1rem;
    }

    aside * {
        margin: 0;
    }

    aside * + * {
        margin: .5rem 0 0 0;
    }
</style>