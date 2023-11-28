<script>
    import { onMount } from 'svelte';
    import MapMenu from '../molecules/MapMenu.svelte';
    import proj4 from 'proj4';
  
    onMount(() => {

        // Setting up map
        var map = L.map('map', {
            center: [52.360956, 4.8964073],
            zoom: 10,
            minZoom: 8
        });

        // Leaflet map theme
        L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}{r}.png',).addTo(map);

        var kansIcon = L.icon({
            iconUrl: '/assets/brightness-svgrepo-com.png',
            iconSize: [32, 32],
            iconAnchor: [16, 32],
        });

        fetch('https://raw.githubusercontent.com/Knetters/FDND-ComponentLibrary/main/static/data/Bodem_Bunnik.geojson')
        .then(response => response.json())
        .then(data => {
            // Looping through the features
            data.features.forEach(feature => {
                // Extracting coordinates
                const coordinates = feature.geometry.coordinates;

                // Define the projection definitions for RD coordinates and WGS84 (latitude/longitude)
                const rdProjection = '+proj=sterea +lat_0=52.15616055555555 +lon_0=5.38763888888889 +k=0.9999079 +x_0=155000 +y_0=463000 +ellps=bessel +units=m +no_defs';
                const wgs84Projection = '+proj=longlat +ellps=WGS84 +datum=WGS84 +no_defs';

                // Define the initial RD coordinates
                const rdCoordinates = [coordinates[0], coordinates[1]];

                // Perform the conversion from RD to WGS84
                const convertedCoordinates = proj4(rdProjection, wgs84Projection, rdCoordinates);

                // Extract latitude and longitude values
                const [longitude, latitude] = convertedCoordinates;

                // Create a custom HTML element
                const customElement = document.createElement('div');
                customElement.innerHTML = `
                    <h3>${feature.properties.Naam}</h3>
                    <p>Other content here...</p>
                `;

                // Display the converted coordinates
                console.log('Latitude:', latitude);
                console.log('Longitude:', longitude);

                var marker = L.marker([latitude, longitude], {
                    icon: kansIcon
                }).addTo(map).bindPopup(customElement);

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