<template>
  <div class="Create">
    <h1>Add New Games To The Database</h1>
    <p>
      All data has been uploaded to the app up until the the end of November,
      2021
    </p>
    <p>Any games since then must be uploaded manually via this site.</p>
    <p>Date: <input type="text" v-model="newScore.date" /></p>
    <div>
      <label>Home Team :</label>
      <select v-model="newScore.home_team">
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
    </div>
    <p></p><div>
      <label>Away Team :</label>
      <select v-model="newScore.away_team">
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
    </div>
     <p>Home Score: <input type="text" v-model="newScore.home_score" /></p>
    <p>Away Score: <input type="text" v-model="newScore.away_score" /></p>
    <p>
      Home Spread: <input type="text" v-model="newScore.closing_spread_home" />
    </p>
    <p>
      Away Spread: <input type="text" v-model="newScore.closing_spread_away" />
    </p>

    <p><button v-on:click="createScore()">Add A New Game</button></p>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      newScore: {
        date: "",
        home_team: "",
        away_team: "",
        home_score: "",
        away_score: "",
        closing_spread_home: "",
        closing_spread_away: "",
      },
    };
  },

  methods: {
    createScore: function () {
      console.log("creating new score...");
      axios
        .post("/scores", {
          input_date: this.newScore.date,
          input_home_team: this.newScore.home_team,
          input_away_team: this.newScore.away_team,
          input_home_score: this.newScore.home_score,
          input_away_score: this.newScore.away_score,
          input_closing_spread_home: this.newScore.closing_spread_home,
          input_closing_spread_away: this.newScore.closing_spread_away,
        })
        .then((response) => {
          console.log(response.data);
        });
    },
  },
};
</script>

<style>
    .center {
        width: 50%;
        margin: 0 auto;
    }
</style>