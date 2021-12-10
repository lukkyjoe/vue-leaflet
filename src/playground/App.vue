<template>
  <map-component :ronde="ronde" class="map"></map-component>
</template>

<script>
import MapComponent from "./MapComponent.vue";

export default {
  name: "App",
  components: {
    MapComponent,
  },
  data() {
    return {
      ronde: undefined,
      timeout: undefined,
    };
  },
  mounted() {
    this.timeout = setTimeout(this.setRonde, 2000);
  },
  beforeUnmount() {
    clearTimeout(this.timeout);
  },
  methods: {
    setRonde() {
      this.ronde = {
        geoJson: {
          type: "FeatureCollection",
          features: [
            {
              type: "Feature",
              properties: {},
              geometry: {
                type: "Polygon",
                coordinates: [
                  [
                    [-12.65625, 34.59704151614417],
                    [18.6328125, 34.59704151614417],
                    [18.6328125, 50.958426723359935],
                    [-12.65625, 50.958426723359935],
                    [-12.65625, 34.59704151614417],
                  ],
                ],
              },
            },
          ],
        },
      };
    },
  },
};
</script>

<style>
.map {
  height: 500px;
  width: 500px;
}
</style>
