<template>
  <div id="testfetch">
{{forecastdays}}
  </div>
</template>
<script>
export default {
  name: "testfetch",
  data() {
    return {
      worlddata: {},
      forecastdays:[],
    }
  },
  beforeMount(){
    this.getName();
  },
  methods: {
    async getName(){
      const res = await fetch('http://api.weatherapi.com/v1/forecast.json?key=b8c9d08fd4574e739bf70228222505&q=London&days=10&aqi=no&alerts=no');
      const data = await res.json();
      this.worlddata = data;
      this.forecastdays = data.forecast.forecastday;
    }
  }
};
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
