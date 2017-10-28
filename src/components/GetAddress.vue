<template>
  <div>
  </div>
</template>

<script>
import GoogleMapsLoader from 'google-maps';

export default {
  name: 'getAddress',
  data () {
    return {
      lat: null,
      lng: null,
      address: null,
      hasGeo: ("geolocation" in navigator),
    }
  },

  methods: {
    getLocation() {
      if (!this.hasGeo) return false;

      navigator.geolocation.getCurrentPosition((position) => {
        this.lat = position.coords.latitude;
        this.lng = position.coords.longitude;

        this.getAddress(this.lat, this.lng);
      });
    },

    getAddress(lat, lng) {
      const vm = this;

      GoogleMapsLoader.load(function(google) {
        const geocoder = new google.maps.Geocoder;

        geocoder.geocode(
          { location: { lat, lng } },
          (results, status) => {
            if (status === 'OK' && results[0]) {
              vm.$emit('input', results[0].formatted_address)
              vm.address = results[0].formatted_address
            }
          }
        );
      });
    }
  },

  created() {
    this.getLocation();
  }
}
</script>
