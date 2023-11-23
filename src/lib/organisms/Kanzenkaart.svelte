<script>
    import { onMount } from 'svelte';
    import MapMenu from '../molecules/MapMenu.svelte';
  
    onMount(() => {

        // Setting up map
        var map = L.map('map', {
            center: [52.360956, 4.8964073],
            zoom: 10,
            minZoom: 2
        });

        // Leaflet map theme
        // L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}{r}.png',).addTo(map);
        L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/Canvas/World_Light_Gray_Base/MapServer/tile/{z}/{y}/{x}',).addTo(map);

        // Loop trough the geojson data
        fetch('https://raw.githubusercontent.com/Knetters/FDND-ComponentLibrary/main/static/data/Bodem_Bunnik.geojson')
        .then(response => response.json())
        .then(data => {

            // Looping through the features
            data.features.forEach(feature => {

            // Extracting coordinates
            const coordinates = feature.geometry.coordinates;

            console.log(coordinates)
            
            // Creating Leaflet circle
            const circle = L.circle([coordinates[1], coordinates[0]], {
                color: 'red', // Circle color
                fillColor: '#f03', // Fill color
                fillOpacity: 0.5, // Fill opacity
                radius: 50 // Circle radius in meters
            }).addTo(map); // Leaflet uses [lat, lng], GeoJSON uses [lng, lat]
            
            // You can customize circles or bind popups here
            circle.bindPopup(`<b>${feature.properties.Naam}</b><br/>ID: ${feature.properties.id}`);
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