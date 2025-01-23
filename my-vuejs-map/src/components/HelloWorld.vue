<template>
  <div id="map" style="height: 100vh;"></div>
</template>

<script>
import { onMounted } from 'vue';
import L from 'leaflet';
import 'leaflet/dist/leaflet.css';

export default {
  name: 'MapComponent',
  setup() {
    onMounted(() => {
      const map = L.map('map').setView([47.7615, -122.2054], 13);

      L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
      }).addTo(map);

      L.marker([47.7615, -122.2054]).addTo(map)
        .bindPopup('A pretty CSS3 popup.<br> Easily customizable.')
        .openPopup();
    });
  }
};
</script>

<style>
#map {
  height: 100vh;
}
</style>
