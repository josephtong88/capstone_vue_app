<template>
  <div class="Score">
    <router-view />
    <header id="header" class="d-flex align-items-center">
      <div class="container d-flex align-items-center justify-content-between">
        <div class="logo">
          <a href="/"
            ><img src="assets/img/logo.png" alt="" class="img-fluid"
          /></a>
        </div>

        <!-- .navbar -->
        <nav id="navbar" class="navbar">
          <ul>
            <li><router-link to="/home">Home</router-link></li>
                  <li><router-link to="/scores">Scores Index</router-link></li>
          </ul>
        </nav>
      </div>
    </header>
    <h1>Scores Index</h1>
    <div
      v-for="score in scores" v-bind:key="score.id">
      <p>Date: {{ score.date }}</p>
      <p>Home Team: {{ score.home_team }}</p>
      <p>Away Team: {{ score.away_team }}</p>
      <p>Home Score: {{ score.home_score }}</p>
      <p>Away Score: {{ score.away_score }}</p>
      <p>Home Spread: {{ score.closing_spread_home }}</p>
      <p>Away Spread: {{ score.closing_spread_away }}</p>
      <p>Did the home team cover? {{ score.home_team_cover }}</p>
      <p>Did the away team cover? {{ score.away_team_cover }}</p>
      <hr>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      scores: [],
    };
  },
  created: function () {
    this.indexscores();
  },
  methods: {
    indexscores: function () {
      axios.get("/scores").then((response) => {
        console.log("scores index", response);
        this.scores = response.data;
      });
    },
    
  },
};
</script>
