<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input
          type="text"
          class="search-bar"
          placeholder="Search..."
          v-model="query"
          @keypress="fetchWeather"
        />
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
import IApp  from "./interfaces/App";
import Vue from "vue";

const app = Vue.createApp<IApp>({});

app.component("app", {
  name: "App",
  data() {
    return {
      api_key: process.env.API_WEATHER_KEY,
      base_url: "https://api.openweathermap.org/data/2.5",
      query: "",
      weather: {},
    };
  },
  methods: {
    fetchWeather(e: any): void {
      if (e.key == "Enter") {
        fetch(
          `${this.base_url}/weather?q=${this.query}&units=&APPID=${this.api_key}`
        )
          .then((res) => {
            return res.json();
          })
          .then(this.setResults);
      }
    },

    setResults(result) {
      this.weather = result;
    },
  },
})
</script>

<style lang="scss" src="./App.scss" />
