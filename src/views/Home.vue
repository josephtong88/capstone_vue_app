<template>
  <div class="home">
    <h1>Scores Index</h1>
    <div
      v-for="score in scores" v-bind:key="score.id">
      <p>Date: {{ score.date }}</p>
      <p>Home Team: {{ score.home_team }}</p>
      <p>Away Team: {{ score.away_team }}</p>
      <p>Home Score: {{ score.home_score }}</p>
      <p>Away Score: {{ score.away_score }}</p>
      <p>Home Spread: {{ score.closing_spread_home }}</p>
      <p>Away SPread: {{ score.closing_spread_away }}</p>
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
