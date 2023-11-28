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

        const value0 = document.getElementById('value0');
        const value1 = document.getElementById('value1');
        const value2 = document.getElementById('value2');
        const value3 = document.getElementById('value3');
        const value4 = document.getElementById('value4');
        const value5 = document.getElementById('value5');
        const value6 = document.getElementById('value6');
        const value7 = document.getElementById('value7');

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

                    // value0.innerHTML = `${feature.properties.Naam}`;
                    // value1.innerHTML = `${feature.properties.Naam}`;
                    // value2.innerHTML = `${feature.properties.Naam}`;
                    // value3.innerHTML = `${feature.properties.Naam}`;
                    // value4.innerHTML = `${feature.properties.Naam}`;
                    // value5.innerHTML = `${feature.properties.Naam}`;
                    // value6.innerHTML = `${feature.properties.Naam}`;
                    // value7.innerHTML = `${feature.properties.Naam}`;
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

            // Get all list items
            const menuItems = document.querySelectorAll('#menu-list li');
        
            menuItems.forEach(item => {
                item.addEventListener('click', function() {
                    menuItems.forEach(item => {
                        item.classList.remove('active');
                    });

                    this.classList.add('active');

                    const location = this.getAttribute('data-location');
                    
                    if (location === 'amsterdam') {
                        // Change the map view for Utrecht
                        map.setView([52.3547418, 4.8215606], 12);
                    }

                    if (location === 'den-haag') {
                        // Change the map view for Utrecht
                        map.setView([52.071731, 4.2274685], 12);
                    }

                    if (location === 'rotterdam') {
                        // Change the map view for Utrecht
                        map.setView([51.9280632, 4.4084283], 12);
                    }

                    if (location === 'utrecht') {
                        // Change the map view for Utrecht
                        map.setView([52.0784901, 5.1140772], 12);
                    }
                    
                });
            });

    }); 
</script>

<section id="map">
    <MapMenu />

    <aside id="infoPanel">
        <div id="infoContent">
            <div class="inner-content">
                <span class="hide" id="hide">Verbergen</span>
                <h2 id="infoTitle">[naam]</h2>

                <p class="no-margin-bot">Extra informatie</p>
                <div class="extra-info-container">
                    <div class="extra-info-titles">
                        <p>K-Waarde:</p>
                        <p>50-75:</p>
                        <p>&#60;25cm:</p>
                        <p>25-50:</p>
                        <p>75-100:</p>
                        <p>100-150:</p>
                        <p>&#62;150cm:</p>
                        <p>Geometry:</p>
                    </div>

                    <div class="extra-info-values">
                        <p id="value0">[waarde]</p>
                        <p id="value1">[waarde]</p>
                        <p id="value2">[waarde]</p>
                        <p id="value3">[waarde]</p>
                        <p id="value4">[waarde]</p>
                        <p id="value5">[waarde]</p>
                        <p id="value6">[waarde]</p>
                        <p id="value7">[waarde]</p>
                    </div>
                </div>
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
        max-width: 20rem;
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

    .hide {
        position: absolute;
        right: 0;
        bottom: 0;
        padding-bottom: 1rem;
        cursor: pointer;
        color: #2B3F5A;
    }

    .hide:hover {
        color: #767676;
    }

    h2 {
        color: var(--spat);
    }

    .no-margin-bot {
        margin-bottom: 0;
        margin-top: 1rem;
    }

    .extra-info-container {
        width: 100%;
        display: flex;
        padding-top: .5rem;
        border-top: #8795aa 1px solid;
    }

    .extra-info-container p {
        margin: 0;
        padding: 0;
    }

    .extra-info-titles {
        width: 50%;
    }

    .extra-info-values {
        width: 50%;
        text-align: right;
    }
</style>