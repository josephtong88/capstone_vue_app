<template>
  <div class="Home">
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
            <li><a class="nav-link scrollto" href="#about">About Me</a></li>
            <li>
              <a class="nav-link scrollto" href="#report_types">Reporting</a>
            </li>
            <li><a class="nav-link scrollto" href="#teams">Teams</a></li>
            <li><a class="nav-link scrollto" href="#create">Create</a></li>
            <li><router-link to="/scores">Scores Index</router-link></li>
          </ul>
        </nav>
      </div>
    </header>
    <!-- End Header -->

    <main id="main">
      <!-- ======= About Us Section ======= -->
      <section id="about" class="about">
        <div class="container">
          <div class="section-title" data-aos="fade-up">
            <h2>About Me</h2>
          </div>

          <div class="row">
            <div class="col-lg-6" data-aos="fade-right">
              <div class="image">
                <img src="assets/img/about.jpg" class="img-fluid" alt="" />
              </div>
            </div>
            <div class="col-lg-6" data-aos="fade-left">
              <div class="content pt-4 pt-lg-0 pl-0 pl-lg-3">
                <h3>The journey of a simple sports enthusiast</h3>
                <p>
                  What began as an enjoyable hobby turned into an expensive
                  habit proffession that, over time, turned back to a hobby.
                </p>
                <p>
                  In watching and researching NFL trends and data, I came to
                  realize:
                </p>
                <ul>
                  <li>
                    <i class="bx bx-caret-right"></i> Consistent data is hard to
                    come by. Data sources constantly change, formats change,
                    reports change...etc.
                  </li>
                  <li>
                    <i class="bx bx-caret-right"></i> Web-based reporting tools
                    are not user friendly. Many require SQL knowledge and prior
                    experience using their database.
                  </li>
                  <li>
                    <i class="bx bx-caret-right"></i> Because much of studying
                    trends and reviewing historical scores is related to
                    sports-betting, it is often tied to shadier sites that may
                    contain malicious links.
                  </li>
                </ul>
                <p>
                  What I do here is try to provide a simplified reporting tool
                  that to track how often wins/losses/covers/ties occur with a
                  simplified set of parameters.
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>
      <hr />
      <!-- End About Us Section -->

      <!-- ======= Services Section ======= -->
      <section id="report_types" class="report_types">
        <div class="container">
          <div class="section-title" data-aos="fade-up">
            <h2>Reporting</h2>
            <p>Keep. It. Simple. Stupid</p>
          </div>

          <div class="row">
            <div class="col-lg-6 order-2 order-lg-1">
              <div class="icon-box mt-5 mt-lg-0" data-aos="fade-up">
                <i class="bx bx-receipt"></i>
                <h4>Data for the last 5+ years</h4>
                <p>
                  Scores and spreads for every game and every team since 2014
                  season.
                </p>
              </div>
              <div
                class="icon-box mt-5"
                data-aos="fade-up"
                data-aos-delay="100"
              >
                <i class="bx bx-cube-alt"></i>
                <h4>Select by team:</h4>
                <p>Filter by what team you want to see results for.</p>
              </div>
              <div
                class="icon-box mt-5"
                data-aos="fade-up"
                data-aos-delay="200"
              >
                <i class="bx bx-images"></i>
                <h4>Select by date:</h4>
                <p>
                  Select a time frame for whatever team you want to see results
                  for.
                </p>
              </div>
              <div
                class="icon-box mt-5"
                data-aos="fade-up"
                data-aos-delay="300"
              >
                <i class="bx bx-shield"></i>
                <h4>Select specific Oponents</h4>
                <p>Filter by what oppents you want to see against your team.</p>
              </div>
            </div>
            <div
              class="image col-lg-6 order-1 order-lg-2"
              style="background-image: url('assets/img/services.jpg')"
              data-aos="fade-left"
              data-aos-delay="100"
            ></div>
          </div>
        </div>
      </section>
      <hr />
      <!-- End Services Section -->

      <!-- ======= Teams Selection Section ======= -->
      <section id="teams" class="teams">
        <div class="container">
          <div class="section-title" data-aos="fade-up">
            <h2>Teams</h2>
            <p>Select any of the teams below to access all of their games</p>
          </div>

          <div class="column_wrapper" data-aos="fade-up" data-aos-delay="100">
            <div v-for="team in teams" v-bind:key="team.id">
              <p>
                Team ID: {{ team.id }}
                <router-link v-bind:to="`/teams/${team.id}`">
                  {{ team.team_name }}</router-link
                >
              </p>
            </div>
          </div>
        </div>
      </section>
      <hr />
      <!-- End Teams Selection Section -->

      <!-- ======= Teams Selection Section ======= -->
      <section id="schedule" class="schedule">
        <div class="container">
          <div class="section-title" data-aos="fade-up">
            <h2>Schedule</h2>
            <div id="DOM_element_id_in_your_website_1639936180795"></div>
          </div>

          
        </div>
      </section>
      <hr />
      <!-- End Teams Selection Section -->
      <!-- ======= Create Section ======= -->
      <section id="create" class="create">
        <div class="container-fluid">
          <div class="row">
            <div
              class="col-lg-7 order-2 order-lg-1 d-flex flex-column justify-content-center align-items-stretch"
            >
              <div class="content" data-aos="fade-up">
                <h3>Add New Games !</h3>
                <p>
                  Due to being in California where sports-betting is illegal,
                  many API's are blocked so a continuous feed of scores/spreads
                  are unavailable. Because of this, all games must be added
                  manually. Please contribute by filling in below to add games
                  to the database.
                </p>
              </div>
              <ul>
                <li>
                  <p>Date: <input type="text" v-model="newScore.date" /></p>
                </li>
                <div>
                  <li><label>Home Team :</label></li>
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
                <p></p>
                <div>
                  <li><label>Away Team :</label></li>
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
                <p></p>
                <li>
                  <p>
                    Home Score:
                    <input type="text" v-model="newScore.home_score" />
                  </p>
                </li>
                <li>
                  <p>
                    Away Score:
                    <input type="text" v-model="newScore.away_score" />
                  </p>
                </li>
                <li>
                  <p>
                    Home Spread:
                    <input type="text" v-model="newScore.closing_spread_home" />
                  </p>
                </li>
                <li>
                  <p>
                    Away Spread:
                    <input type="text" v-model="newScore.closing_spread_away" />
                  </p>
                </li>
              </ul>
              <p><button v-on:click="createScore()">Add A New Game</button></p>
            </div>

            <div
              class="col-lg-5 order-1 order-lg-2 align-items-stretch video-box"
              style="background-image: url('assets/img/why-us.jpg')"
              data-aos="zoom-in"
            >
              <a
                href="https://www.youtube.com/watch?v=LIqQNG_q2us"
                class="venobox play-btn mb-4"
                data-vbtype="video"
                data-autoplay="true"
              ></a>
            </div>
          </div>
        </div>
      </section>
      <!-- End Create Section -->

      <!-- ======= Team Section ======= -->
      <section id="team" class="team">
        <div class="container">
          <div class="section-title" data-aos="fade-up">
            <h2>Team</h2>
            <p>
              Magnam dolores commodi suscipit eius consequatur ex aliquid fuga
              eum quidem
            </p>
          </div>

          <div class="row">
            <div class="col-lg-4 col-md-6 d-flex align-items-stretch">
              <div class="member" data-aos="zoom-in">
                <div class="member-img">
                  <img
                    src="assets/img/team/team-1.jpg"
                    class="img-fluid"
                    alt=""
                  />
                  <div class="social">
                    <a href=""><i class="bi bi-twitter"></i></a>
                    <a href=""><i class="bi bi-facebook"></i></a>
                    <a href=""><i class="bi bi-instagram"></i></a>
                    <a href=""><i class="bi bi-linkedin"></i></a>
                  </div>
                </div>
                <div class="member-info">
                  <h4>Walter White</h4>
                  <span>Chief Executive Officer</span>
                  <p>
                    Animi est delectus alias quam repellendus nihil nobis dolor.
                    Est sapiente occaecati et dolore. Omnis aut ut nesciunt
                    explicabo qui. Eius nam deleniti ut omnis
                  </p>
                </div>
              </div>
            </div>

            <div class="col-lg-4 col-md-6 d-flex align-items-stretch">
              <div class="member" data-aos="zoom-in" data-aos-delay="100">
                <div class="member-img">
                  <img
                    src="assets/img/team/team-2.jpg"
                    class="img-fluid"
                    alt=""
                  />
                  <div class="social">
                    <a href=""><i class="bi bi-twitter"></i></a>
                    <a href=""><i class="bi bi-facebook"></i></a>
                    <a href=""><i class="bi bi-instagram"></i></a>
                    <a href=""><i class="bi bi-linkedin"></i></a>
                  </div>
                </div>
                <div class="member-info">
                  <h4>Sarah Jhonson</h4>
                  <span>Product Manager</span>
                  <p>
                    Aspernatur iste esse aliquam enim et corporis. Molestiae
                    voluptatem aut eligendi quis aut. Libero vel amet voluptatem
                    eos rerum non doloremque
                  </p>
                </div>
              </div>
            </div>

            <div class="col-lg-4 col-md-6 d-flex align-items-stretch">
              <div class="member" data-aos="zoom-in" data-aos-delay="200">
                <div class="member-img">
                  <img
                    src="assets/img/team/team-3.jpg"
                    class="img-fluid"
                    alt=""
                  />
                  <div class="social">
                    <a href=""><i class="bi bi-twitter"></i></a>
                    <a href=""><i class="bi bi-facebook"></i></a>
                    <a href=""><i class="bi bi-instagram"></i></a>
                    <a href=""><i class="bi bi-linkedin"></i></a>
                  </div>
                </div>
                <div class="member-info">
                  <h4>William Anderson</h4>
                  <span>CTO</span>
                  <p>
                    Ut enim possimus nihil cupiditate beatae. Veniam facere quae
                    non qui necessitatibus rerum eos vero. Maxime sit sunt quo
                    dolor autem est qui quaerat
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>

       
      </section>
      <!-- End Team Section -->
    </main>
    <!-- End #main -->
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      teams: [],
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
(function (b, s, p, o, r, t) {
  b["broadage"] = b["broadage"] || [];
  if (!b["broadage"].length) {
    r = document.createElement(s);
    t = document.getElementsByTagName(s)[0];
    r.async = true;
    r.src = p;
    t.parentNode.insertBefore(r, t);
  }
  b["broadage"].push({
    bundleId: o.bundleId,
    widgets: o.widgets,
    accountId: o.accountId,
  });
})(window, "script", "//cdn-saas.broadage.com/widgets/loader/loader.js", {
  bundleId: ["football-fx"],
  accountId: "ebc86948-925f-4dce-b95c-1f8d76d6bdcf",
  widgets: {
    footballFixture: [
      {
        element: "DOM_element_id_in_your_website_1639936180795",
        tournamentId: 1,
      },
    ],
  },
});
</script>
