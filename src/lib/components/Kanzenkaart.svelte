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
  
    }); 
</script>
  
<section id="map">
    <div class="map-menu">
        <div class="text-block">
            <h1>Kanzenkaart</h1>
            <p>Kleine regel tekst met uitleg over de kaart</p>
        </div>
        <div class="action-block">
            <p>min</p>
            <ul>
                <li class="active">Filteroptie</li>
                <li>Filteroptie</li>
                <li>Filteroptie</li>
                <li>Filteroptie</li>
            </ul>
        </div>
    </div>
</section>
  
<style>
    section {
        height: 93vh;
        width: 100vw;
        margin-top: 7vh;
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
        transition: .2s;
    }

    .action-block ul li:hover {
        background-color: #4ECD5D;
        color: #fff;
    }
</style>