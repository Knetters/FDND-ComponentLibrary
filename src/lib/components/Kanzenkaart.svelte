<script>
    import { onMount } from 'svelte';
  
    onMount(() => {

        // Setting up map
        var map = L.map('map', {
            center: [52.360956, 4.8964073],
            zoom: 10,
            minZoom: 8
        });

        // Leaflet map theme
        L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/Canvas/World_Light_Gray_Base/MapServer/tile/{z}/{y}/{x}',).addTo(map);

        // menu logic
        const mapMenu = document.getElementById("map-menu")
        const menuList = document.getElementById("menu-list")
        const menuText = document.getElementById("menu-text")
        const min = document.getElementById("min")
        const plus = document.getElementById("plus")

        let menuToggled = false
        plus.style.display = "none"

        min.addEventListener("click", toggleMenu);
        plus.addEventListener("click", toggleMenu);

        function toggleMenu() {
            if (menuToggled == false) {
                mapMenu.style.width = "20%";
                mapMenu.style.height = "3rem";
                menuList.style.display = "none";
                menuText.style.display = "none";

                plus.style.display = "block"
                min.style.display = "none"

                menuToggled = true
            } else {
                mapMenu.style.width = "90%";
                mapMenu.style.height = "5rem";
                menuList.style.display = "block";
                menuText.style.display = "block";

                plus.style.display = "none"
                min.style.display = "block"

                menuToggled = false
            }
        }
    }); 
</script>
  
<section id="map">
    <div id="map-menu" class="map-menu">
        <div class="text-block">
            <h1>Kanzenkaart</h1>
            <p id="menu-text">Kleine regel tekst met uitleg over de kaart</p>
        </div>
        <div class="action-block">
            <p id="min" class="menu-icon">Verbergen</p>
            <p id="plus" class="menu-icon">Opties</p>
            <ul id="menu-list">
                <li>Filteroptie</li>
                <li>Filteroptie</li>
                <li>Filteroptie</li>
                <li class="active">Filteroptie</li>
            </ul>
        </div>
    </div>
</section>
  
<style>
    section {
        height: 92vh;
        width: 100vw;
        margin-top: 8vh;
        position: absolute;
    }

    .map-menu {
        background-color: #fdfdfd;
        height: 5rem;
        width: 90%;
        margin-left: 5%;
        margin-top: 1rem;
        padding: .5rem 1rem;
        border-radius: 1rem;
        position: relative;
        z-index: 9999;
        display: flex;
        box-shadow: 0px 0px 10px 5px #9d9d9d4b;
        transition: .2s;
    }

    .text-block {
        width: 50%;
        position: relative;
    }

    h1 {
        padding: 0rem;
        margin-top: -.2rem;
        font-size: 1.5rem;
        color: var(--spat);
    }

    .text-block p {
        position: absolute;
        bottom: 0;
        margin: 0;
        transition: .2s;
    }

    .action-block {
        width: 50%;
        position: relative;
        text-align: right;
    }

    .action-block ul {
        list-style: none;
        padding: 0;
        margin: 0;
        position: absolute;
        bottom: 0;
        right: 0;
    }

    .action-block ul li {
        float: right;
        background-color: #f2f2f2;
        margin-left: 1rem;
        padding: .2rem .6rem;
        cursor: pointer;
        -webkit-user-select: none; /* Safari */
        -ms-user-select: none; /* IE 10 and IE 11 */
        user-select: none; /* Standard syntax */
        border-radius: .5rem;
    }

    .action-block ul li:hover {
        background-color: #4ECD5D;
        color: #fff;
    }

    .active {
        background-color: #4ECD5D !important;
        color: #fff;
    }

    .menu-icon {
        cursor: pointer;
        color: #2B3F5A;
    }

    .menu-icon:hover {
        color: #767676;
    }
</style>