<template>
  <div id="mapContainer">
    <l-map>
      <l-geo-json
        layer-type="overlay"
        name="Ronde"
        v-if="ronde"
        :geojson="ronde.geoJson"
      />
      <l-control-layers position="bottomright" />
    </l-map>
  </div>
</template>

<script>
import LMap from "../components/LMap.vue";
import LControlLayers from "../components/LControlLayers.vue";
import LGeoJson from "../components/LGeoJson.vue";
import "leaflet/dist/leaflet.css";

export default {
  components: {
    LMap,
    LControlLayers,
    LGeoJson,
  },
  props: {
    ronde: Object,
  },
};
</script>
