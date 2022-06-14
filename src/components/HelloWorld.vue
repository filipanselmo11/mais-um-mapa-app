<template>
  <div id="map"></div>
</template>

<script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";
// const L = window["L"];
export default {
  name: "HelloWorld",
  data: () => ({
    map: undefined,
  }),
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      this.map = L.map("map").setView([-25.46033726712044, -49.29804536309487], 13);
      L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
        maxZoom: 19,
        attribution:
          '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
      }).addTo(this.map);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#map {
  height: 100%;
  width: 100%;
  z-index: 1;
}
</style>
