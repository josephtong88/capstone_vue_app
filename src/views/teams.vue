<template>
  <div class="Teams">
    <h1>{{ team.team_name }}</h1>
<p> Select date parameters if required between:</p>
    <p><input type="text" v-model="start_date"> start date </p>
    <p><input type="text" v-model="end_date"> end date </p>

    <select v-model="opp">
                    <option disabled value="">Please select one</option>
                    <option>Washington Football Team</option>
                    <option>Baltimore Ravens</option>
                    <option>Green Bay Packers</option>
                    <option>San Francisco 49ers</option>
                    <option>Denver Broncos</option>
                    <option>Cincinnati Bengals</option>
                    <option>Houston Texans</option>
                    <option>Indianapolis Colts</option>
                    <option>Jacksonville Jaguars</option>
                    <option>Miami Dolphins</option>
                    <option>New England Patriots</option>
                    <option>New York Giants</option>
                    <option>New Orleans Saints</option>
                    <option>Dallas Cowboys</option>
                    <option>Detroit Lions</option>
                    <option>Tampa Bay Buccaneers</option>
                    <option>Los Angeles Chargers</option>
                    <option>Kansas City Chiefs</option>
                    <option>Seattle Seahawks</option>
                    <option>Las Vegas Raiders</option>
                    <option>Buffalo Bills</option>
                    <option>Carolina Panthers</option>
                    <option>Chicago Bears</option>
                    <option>Cleveland Browns</option>
                    <option>Minnesota Vikings</option>
                    <option>New York Jets</option>
                    <option>Philadelphia Eagles</option>
                    <option>Tennessee Titans</option>
                    <option>Atlanta Falcons</option>
                    <option>Arizona Cardinals</option>
                    <option>Pittsburgh Steelers</option>
                    <option>Los Angeles Rams</option>
                  </select>

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
      end_date: "",
      opp:""
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
      axios.get(`/datedteams/${this.$route.params.id}?start_date=${this.start_date}&end_date=${this.end_date}&opp=${this.opp}`).then((response) => {
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
