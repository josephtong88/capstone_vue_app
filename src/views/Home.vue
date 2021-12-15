<template>
  <div class="Home">
    <h1>Team Index</h1>
    <div v-for="team in teams" v-bind:key="team.id">
      <p>
        Team ID: {{ team.id }}
        <router-link v-bind:to="`/teams/${team.id}`">
          {{ team.team_name }}</router-link
        >
      </p>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      teams: [],
    };
  },
  created: function () {
    this.indexteams();
  },
  methods: {
    indexteams: function () {
      axios.get("/teams").then((response) => {
        console.log("teams index", response);
        this.teams = response.data;
      });
    },
  },
};
</script>
