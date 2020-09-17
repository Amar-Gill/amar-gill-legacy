<script>
  import { fly } from "svelte/transition";
  import { onMount, createEventDispatcher } from "svelte";

  let activeProjectTitle; // used to style currently selected project
  let marker;

  export let map;
  export let beProjects;
  export let energyProjects;
  export let sustainabilityProjects;

  const dispatch = createEventDispatcher();

  function handleClick(project) {
    map.panTo(project.center);
    map.setZoom(17);

    // add marker
    if (!marker) {
      marker = new google.maps.Marker({
        map,
        position: project.center
      });
    } else {
      marker.setPosition(project.center);
    }

    dispatch("select", {
      project: project
    });

    // set active project to the clicked project to activate highlighting
    activeProjectTitle = project.title;
  }
</script>

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
    box-shadow: 0.5rem 0.5rem var(--compliment-1);
    color: var(--compliment-2);
  }

  summary {
      cursor: pointer;
  }

  @media (min-width: 451px) and (max-width: 835px) {
    .dropdown-btn {
      font-size: 1.25rem;
    }

    .menu-container {
      width: 14rem;
    }
  }

  @media (max-width: 450px) {
    .dropdown-btn {
      font-size: 1rem;
    }

    .menu-container {
      width: 12rem;
    }
  }

  .dropdown-container {
    display: none;
    border-radius: 9px;
    margin: 0;
  }

  p {
    /* margin: 0 0 0.5rem 2rem; */
    cursor: pointer;
  }

  p:hover {
    color: var(--compliment-1);
  }

  [aria-current] {
    color: var(--hue-3);
    font-weight: 600;
  }

  [aria-current]:hover {
    color: var(--hue-3);
  }
</style>

<div in:fly={{ x: -200, duration: 800 }} class="menu-container">

  <details>
    <summary>Power Generation</summary>
    {#each energyProjects as eProject, i}
      <p
        aria-current={activeProjectTitle === eProject.title ? true : undefined}
        on:click={() => handleClick(eProject)}>
        {i + 1}: {eProject.title}
      </p>
    {/each}
  </details>

  <details>
    <summary>Building Envelope</summary>
    {#each beProjects as beProject, i}
      <p
        aria-current={activeProjectTitle === beProject.title ? true : undefined}
        on:click={() => handleClick(beProject)}>
        {i + 1}: {beProject.title}
      </p>
    {/each}
  </details>

  <details>
    <summary>Green Buildings</summary>
    {#each sustainabilityProjects as sProject, i}
      <p
        aria-current={activeProjectTitle === sProject.title ? true : undefined}
        on:click={() => handleClick(sProject)}>
        {i + 1}: {sProject.title}
      </p>
    {/each}
  </details>

</div>
