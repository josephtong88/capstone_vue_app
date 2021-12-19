<template>

  <div class="Teams">
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
    <h1>{{ team.team_name }}</h1>
    <p>Select date parameters if required between:</p>
    <p><input type="text" v-model="start_date" /> start date</p>
    <p><input type="text" v-model="end_date" /> end date</p>
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
<p></p>
    <ul><li><button v-on:click="datedindexscores">Search By Date Range</button></li><p></p>
    <li><button v-on:click="oppindexscores">Search by Opponent</button></li><p></p>
  <li><button v-on:click="datedoppsindexscores">
      Search by Date Range and Opponent
  </button></li><p></p>
  
    <li><button v-on:click="homescores">All Home Games</button></li><p></p>
    <li><button v-on:click="awayscores">All Away Games</button></li><p></p>
    </ul>
    <hr>
    {{ record }}
    <hr>
    <div v-for="score in scores" v-bind:key="score.id">
      <p>Date: {{ score.date }}</p>
      <p>Home Team: {{ score.home_team }} ({{ score.closing_spread_home }})</p>
      <p>Away Team: {{ score.away_team }} ({{ score.closing_spread_away }})</p>
      <p></p>
      <p>
        Final Score: {{ score.home_team }}: {{ score.home_score }} to
        {{ score.away_team }}: {{ score.away_score }}.
      </p>
      <p>Did the home team cover? {{ score.home_team_cover }}</p>
      <p>Did the away team cover? {{ score.away_team_cover }}</p>
    </div>
      <hr />
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
      opp: "",
      record: "",
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
        this.scores = response.data.scores;
        this.record = response.data.record;
      });
    },
    datedindexscores: function () {
      axios
        .get(
          `/datedteams/${this.$route.params.id}?start_date=${this.start_date}&end_date=${this.end_date}`
        )
        .then((response) => {
          console.log("scores index", response);
          this.scores = response.data.scores;
          this.record = response.data.record;
        });
    },
    datedoppsindexscores: function () {
      axios
        .get(
          `/datedoppteams/${this.$route.params.id}?start_date=${this.start_date}&end_date=${this.end_date}&opp=${this.opp}`
        )
        .then((response) => {
          console.log("scores index", response);
          this.scores = response.data.scores;
            this.record = response.data.record;
        });
    },

    oppindexscores: function () {
      axios
        .get(`/oppteams/${this.$route.params.id}?opp=${this.opp}`)
        .then((response) => {
          console.log("scores index", response);
           this.scores = response.data.scores;
            this.record = response.data.record;
        });
    },

    showteam: function () {
      axios.get("/showteams/" + this.$route.params.id).then((response) => {
        console.log("Team Name", response);
        this.team = response.data;
      });
    },
    homescores: function () {
      axios.get(`/hometeams/${this.$route.params.id}`).then((response) => {
        console.log("scores index", response);
        this.scores = response.data.scores;
        this.record = response.data.record;
      });
    },
    awayscores: function () {
      axios.get(`/awayteams/${this.$route.params.id}`).then((response) => {
        console.log("scores index", response);
        this.scores = response.data.scores;
        this.record = response.data.record;
      });
    },
  },
};
</script>
