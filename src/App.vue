<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search..." />
      </div>

      <div class="weather-wrap">
        <div class="location-box">
          <div class="location">Salvador, BA</div>
          <div class="date">Sunday 28 November 2021</div>
        </div>

        <div class="weather-box">
          <div class="temperature">25°C</div>
          <div class="weather">Rain</div>
        </div>
      </div>
    </main>
  </div>
</template>

<script lang="ts">
export default {
  name: "App",
  data: () => ({
    api_key: process.env.API_WEATHER_KEY,
  }),
};
</script>

<style lang="scss" src="./App.scss" />
