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

  function handleClickDetails(e) {
    const details = document.querySelectorAll("details");

    for (const detail of details) {
      if (detail !== e.target.parentNode) {
        detail.removeAttribute("open");
      }
    }
  }

  function handleClick(project) {
    map.panTo(project.center);
    map.setZoom(17);

    // add marker
    if (!marker) {
      marker = new google.maps.Marker({
        map,
        position: project.center,
      });
    } else {
      marker.setPosition(project.center);
    }

    dispatch("select", {
      project: project,
    });

    // set active project to the clicked project to activate highlighting
    activeProjectTitle = project.title;
  }

  onMount(() => {});
</script>

<style>
  @import url("https://fonts.googleapis.com/css?family=Karla|Space+Mono");

  div {
    z-index: 2;
    top: 9%;
    position: fixed;
    width: 21rem;
    left: 1%;
    background-color: var(--hue-1);
    border-radius: 9px;
    box-shadow: 0.5rem 0.5rem var(--compliment-1);
    color: var(--compliment-2);
    font-family: "Space Mono", monospace;
  }

  details {
    padding-left: 0.5rem;
    padding-right: 0.5rem;
    padding-bottom: 0.5rem;
  }

  summary {
    cursor: pointer;
    font-size: 1.5rem;
    list-style-type: none;
    /* border-bottom: 2px solid; */
  }

  section {
    overflow: auto;
    margin-left: 1rem;
    padding-left: 1rem;
    border-left: 1px solid;
  }

  :global(details[open] > section) {
    animation-name: slideDown;
    animation-duration: 0.3s;
    animation-fill-mode: forwards;
  }

  @media (min-width: 451px) and (max-width: 835px) {
    summary {
      font-size: 1.25rem;
    }

    div {
      width: 14rem;
    }
  }

  @media (max-width: 450px) {
    summary {
      font-size: 1rem;
    }

    div {
      width: 12rem;
    }
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

  @keyframes slideDown {
    from {
      opacity: 0;
      max-height: 0;
    }
    to {
      opacity: 1;
      max-height: 20vh;
    }
  }
</style>

<div in:fly={{ x: -200, duration: 800 }} class="menu-container">
  <details>
    <summary on:click={(e) => handleClickDetails(e)}>Power Generation</summary>
    <section>
      {#each energyProjects as eProject, i}
        <p
          aria-current={activeProjectTitle === eProject.title ? true : undefined}
          on:click={() => handleClick(eProject)}>
          {i + 1}: {eProject.title}
        </p>
      {/each}
    </section>
  </details>

  <details>
    <summary on:click={(e) => handleClickDetails(e)}>Building Envelope</summary>
    <section>
      {#each beProjects as beProject, i}
        <p
          aria-current={activeProjectTitle === beProject.title ? true : undefined}
          on:click={() => handleClick(beProject)}>
          {i + 1}: {beProject.title}
        </p>
      {/each}
    </section>
  </details>

  <details>
    <summary on:click={(e) => handleClickDetails(e)}>Green Buildings</summary>
    <section>
      {#each sustainabilityProjects as sProject, i}
        <p
          aria-current={activeProjectTitle === sProject.title ? true : undefined}
          on:click={() => handleClick(sProject)}>
          {i + 1}: {sProject.title}
        </p>
      {/each}
    </section>
  </details>
</div>
