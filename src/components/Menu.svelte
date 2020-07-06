<div class="menu-container">
    <button class="dropdown-btn">Energy
        <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-container" id="energy-list">
    </div>
    <button class="dropdown-btn">Building Envelope
        <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-container" id="be-list">
    </div>
    <button class="dropdown-btn">Sustainability
        <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-container" id="sustainability-list">
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
        /* height: 40vh; */
        width: 16rem;
        left: 1%;
        background-color: whitesmoke;
        border-radius: 9px;
    }

    .dropdown-btn {
        text-decoration: none;
        font-size: 1.5rem;
        color: #818181;
        display: block;
        border: none;
        background: none;
        width: 100%;
        text-align: left;
        cursor: pointer;
        outline: none;
        margin-bottom: 1rem;
    }


    .dropdown-container {
        display: none;
        background-color: whitesmoke;
        border-radius: 9px;
        margin: 0;
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

    import { onMount } from 'svelte';

    // use map.panTo(element.center) to change center value of map object
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

        // CODE FOR BINDING MAPS FUNCTIONALITY TO LINKS
        let beList = document.getElementById("be-list");

        beProjects.forEach((element, index) => {
            let listItem = document.createElement("p");

            listItem.innerText = element.title;
            listItem.style.margin = "0 0 .5rem 2rem"
            listItem.style.cursor = "pointer";

            listItem.addEventListener('mouseenter', e => {
                listItem.style.color = "pink";
            });

            listItem.addEventListener('mouseleave', e => {
                listItem.style.color = "black";
            });

            // add event listener to pan to the projects coordinates when list item is clicked
            listItem.addEventListener("click", () => {
                map.panTo(element.center);
                map.setZoom(17);

                // add marker
                let marker = new google.maps.Marker({
                    map,
                    position: element.center
                })
            })

            beList.append(listItem)
        })

        let energyList = document.getElementById("energy-list");

        energyProjects.forEach((element, index) => {
            let listItem = document.createElement("p");

            listItem.innerText = element.title;
            listItem.style.margin = "0 0 .5rem 2rem"
            listItem.style.cursor = "pointer";

            listItem.addEventListener('mouseenter', e => {
                listItem.style.color = "pink";
            });

            listItem.addEventListener('mouseleave', e => {
                listItem.style.color = "black";
            });

            // add event listener to pan to the projects coordinates when list item is clicked
            listItem.addEventListener("click", () => {
                map.panTo(element.center);
                map.setZoom(17);

                // add marker
                let marker = new google.maps.Marker({
                    map,
                    position: element.center
                })
            })

            energyList.append(listItem)
        })

        let sustainabilityList = document.getElementById("sustainability-list");

        sustainabilityProjects.forEach((element, index) => {
            let listItem = document.createElement("p");

            listItem.innerText = element.title;
            listItem.style.margin = "0 0 .5rem 2rem"
            listItem.style.cursor = "pointer";

            listItem.addEventListener('mouseenter', e => {
                listItem.style.color = "pink";
            });

            listItem.addEventListener('mouseleave', e => {
                listItem.style.color = "black";
            });

            // add event listener to pan to the projects coordinates when list item is clicked
            listItem.addEventListener("click", () => {
                map.panTo(element.center);
                map.setZoom(17);

                // add marker
                let marker = new google.maps.Marker({
                    map,
                    position: element.center
                })
            })

            sustainabilityList.append(listItem)
        })

    })

</script>