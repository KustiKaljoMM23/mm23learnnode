<script setup>
import L from 'leaflet';
import 'leaflet/dist/leaflet.css';
import 'leaflet/dist/images/marker-icon.png';
import 'leaflet/dist/images/marker-shadow.png';
import { onMounted } from 'vue';
let map = null;
onMounted(() => {
    map = L.map('map').setView([51.505, -0.09], 13);
    L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
        maxZoom: 19,
        attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
    }).addTo(map);

    let marker = L.marker([59.4270, 24.7436]).addTo(map);

    let polygon = L.polygon([
    [59.4277, 24.6312],
    [59.4273, 24.6319],
    [59.4270, 24.6312]
]).addTo(map);
});

function goTo(coords, zoom){
    map.flyTo(coords, zoom);
}

</script>
<template>
    <button class="button is-primary" @click="goTo([59.4270, 24.7436], 18)">Go To School</button>
    <button class="button is-primary" @click="goTo([59.4273, 24.6313], 18)">Go To Home</button>
    <div id="map"></div>
</template>
<style scoped>
#map {
     height: 90vh; 
}
</style>