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
            iconUrl: '/assets/star-svgrepo-com.png',
            iconSize: [32, 32],
            iconAnchor: [16, 32],
        });

        // Reference to the info panel and its content area
        const infoPanel = document.getElementById('infoPanel');
        const infoContent = document.getElementById('infoContent');

        const infoTitle = document.getElementById('infoTitle');

        document.getElementById('hide').addEventListener("click", hideInfo);

        function hideInfo() {
            infoPanel.style.display = "none";
        }

        // Fetching data and working with markers
        fetch('https://raw.githubusercontent.com/Knetters/FDND-ComponentLibrary/main/static/data/Bodem_Bunnik.geojson')
            .then(response => response.json())
            .then(data => {
                // Reference to the info panel and its content area
                const infoPanel = document.getElementById('infoPanel');
                const infoContent = document.getElementById('infoContent');

                // Function to update the panel content based on marker data
                function updateInfoPanel(feature) {
                    infoTitle.innerHTML = `${feature.properties.Naam}`;
                }

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

                    // Create a marker
                    const marker = L.marker([latitude, longitude], {
                        icon: kansIcon 
                    }).addTo(map);

                    // Event listener for marker click
                    marker.on('click', function () {
                        // Update the info panel content when a marker is clicked
                        updateInfoPanel(feature);
                        infoPanel.style.display = "block"
                    });
                });
            })
            .catch(error => {
                console.log('Error fetching data:', error);
            });

    }); 
</script>

<section id="map">
    <MapMenu />

    <aside id="infoPanel">
        <div id="infoContent">
            <div class="inner-content">
                <span id="hide">Verbergen</span>
                <h2 id="infoTitle">[naam]</h2>
            </div>
        </div>
    </aside>
</section>
  
<style>
    section {
        height: 93vh;
        width: 100vw;
        margin-top: 7vh;
        position: absolute;
    }

    aside {
        background-color: #fdfdfdb3;
        height: 70vh;
        width: 20rem;
        margin-left: 5%;
        margin-top: 1.5rem;
        padding: .5rem 1rem;
        border-radius: 1rem;
        position: relative;
        z-index: 9999;
        display: flex;
        box-shadow: 0px 0px 10px 5px #9d9d9d4b;
        transition: .2s;
        display: none;
    }

    .inner-content {
        position: relative;
        width: 100%;
        height: 70vh;
    }

    .inner-content span {
        position: absolute;
        right: 0;
        bottom: 0;
        padding-bottom: 1rem;
        cursor: pointer;
        color: #2B3F5A;
    }

    .inner-content span:hover {
        color: #767676;
    }

    h2 {
        color: var(--spat);
    }
</style>