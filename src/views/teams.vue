<template>
  <div class="Teams">
    <h1>{{ team.team_name }}</h1>
<p> Select date parameters if required between:</p>
    <p><input type="text" v-model="start_date"> start date </p>
    <p><input type="text" v-model="end_date"> end date </p>
    <button v-on:click="datedindexscores" > Submit </button>
    <div v-for="score in scores" v-bind:key="score.id">
      <p>Date: {{ score.date }}</p>
      <p>Home Team: {{ score.home_team }} ({{ score.closing_spread_home }})</p>
      <p>Away Team: {{ score.away_team }} ({{ score.closing_spread_away }})</p>
      <p></p>
      <p>Final Score: {{ score.home_team }}: {{ score.home_score }} to {{ score.away_team }}: {{ score.away_score }}. </p>
     
      <p>Did the home team cover? {{ score.home_team_cover }}</p>
      <p>Did the away team cover? {{ score.away_team_cover }}</p>
      <hr />
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
      message: "Hello from Script (JS)",
      team: {},
      start_date: "",
      end_date: ""
    };
  },
  created: function () {
    this.indexscores();
    this.showteam();
  },
  methods: {
    indexscores: function () {
      axios.get(`/teams/${this.$route.params.id}`).then((response) => {
        console.log("scores index", response);
        this.scores = response.data;
      });
    },
    datedindexscores: function () {
      axios.get(`/datedteams/${this.$route.params.id}?start_date=${this.start_date}&end_date=${this.end_date}`).then((response) => {
        console.log("scores index", response);
        this.scores = response.data;
      });
    },
    showteam: function () {
      axios.get("/showteams/" + this.$route.params.id).then((response) => {
        console.log("Team Name", response);
        this.team = response.data;
      });
    },
  },
};
</script>
