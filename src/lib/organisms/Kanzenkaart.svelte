<script>
    import { onMount } from 'svelte';
    import MapMenu from '../molecules/MapMenu.svelte';
  
    onMount(() => {

        // Setting up map
        var map = L.map('map', {
            center: [52.360956, 4.8964073],
            zoom: 10,
            minZoom: 8
        });

        // Leaflet map theme
        L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}{r}.png',).addTo(map);
        // L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/Canvas/World_Light_Gray_Base/MapServer/tile/{z}/{y}/{x}',).addTo(map);

        fetch('https://raw.githubusercontent.com/Knetters/FDND-ComponentLibrary/main/static/data/Bodem_Bunnik.geojson')
    .then(response => response.json())
    .then(data => {
        // Looping through the features
        data.features.forEach(feature => {
            // Extracting coordinates
            const coordinates = feature.geometry.coordinates;

            // Extracting GPS coordinates
            let gpsLat = coordinates[1];
            let gpsLong = coordinates[0];

            // Converting GPS coordinates to regular coordinates
            let regularLat = gpsLong;
            let regularLong = gpsLat;

            // Your Leaflet.js implementation using regularLat and regularLong
            L.marker([regularLat, regularLong]).addTo(map);
        });
    })
    .catch(error => {
        console.log('Error fetching data:', error);
    });

    }); 
</script>
  
<section id="map">
    <MapMenu />
</section>
  
<style>
    section {
        height: 93vh;
        width: 100vw;
        margin-top: 7vh;
        position: absolute;
    }
</style>