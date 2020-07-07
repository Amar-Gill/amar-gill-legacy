<div class="menu-container">

    <button class="dropdown-btn">Power Generation
        <i class="fa fa-caret-down"></i>
    </button>

    <div class="dropdown-container" >

        {#each energyProjects as eProject, i}
            <p on:click="{() => handleClick(eProject)}" >
                {i + 1}: {eProject.title}
            </p>
        {/each}

    </div>
    
    <button class="dropdown-btn">Building Envelope
        <i class="fa fa-caret-down"></i>
    </button>

    <div class="dropdown-container" >

        {#each beProjects as beProject, i}
            <p on:click="{() => handleClick(beProject)}" >
                {i + 1}: {beProject.title}
            </p>
        {/each}

    </div>

    <button class="dropdown-btn">Green Buildings
        <i class="fa fa-caret-down"></i>
    </button>

    <div class="dropdown-container" >

        {#each sustainabilityProjects as sProject, i}
            <p on:click="{() => handleClick(sProject)}" >
                {i + 1}: {sProject.title}
            </p>
        {/each}

    </div>

</div>

<!-- use tutorial for drawer menu -->
<!-- https://www.w3schools.com/howto/howto_js_dropdown_sidenav.asp -->

<style>
    .menu-container {
        z-index: 2;
        top: 9%;
        position: fixed;
        display: flex;
        flex-direction: column;
        width: 16rem;
        left: 1%;
        background-color: var(--hue-1);
        border-radius: 9px;
        box-shadow: .5rem .5rem var(--compliment-1);
        color: var(--compliment-2);
    }

    .dropdown-btn {
        text-decoration: none;
        font-size: 1.5rem;
        display: block;
        border: none;
        background: none;
        width: 100%;
        text-align: left;
        cursor: pointer;
        outline: none;
        margin-bottom: 1rem;
        color: inherit;
    }

    .dropdown-container {
        display: none;
        border-radius: 9px;
        margin: 0;
    }

    p {
        margin: 0 0 .5rem 2rem;
        cursor: pointer;
    }

    p:hover{
        color: var(--compliment-1);
    }

    .active {
        background-color: green;
        color: white;
    }

    .fa-caret-down {
        float: right;
    }
</style>

<script>
    export let map;

    export let beProjects;
    export let energyProjects;
    export let sustainabilityProjects;

    import { onMount, createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    function handleClick(project) {

        map.panTo(project.center);
        map.setZoom(17);

        // add marker
        let marker = new google.maps.Marker({
            map,
            position: project.center
        })

        dispatch("select", {
            project: project
        })
    }

    onMount(() => {
        // CODE FOR BINDING DROPDOWN DRAWER BEHAVIOR TO MENU BUTTONS
        let dropdown = document.getElementsByClassName("dropdown-btn");

        for (let i = 0; i < dropdown.length; i++) {
            dropdown[i].addEventListener("click", function () {
                this.classList.toggle("active");
                var dropdownContent = this.nextElementSibling;
                if (dropdownContent.style.display === "block") {
                    dropdownContent.style.display = "none";
                } else {
                    dropdownContent.style.display = "block";
                }
            });
        }
    })

</script>