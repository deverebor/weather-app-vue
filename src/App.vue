<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search..." />
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
