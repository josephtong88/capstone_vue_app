<template>
  <div id="app">
    <router-view />
    <header id="header" class="d-flex align-items-center">
      <div class="container d-flex align-items-center justify-content-between">
        <div class="logo">
          <a href="index.html"
            ><img src="assets/img/logo.png" alt="" class="img-fluid"
          /></a>
        </div>

        <nav id="navbar" class="navbar">
          <ul>
            <li><router-link to="/home">Home</router-link></li>
          </ul>
        </nav>
      </div>
    </header>
    <!-- End Header -->

    <!-- ======= Footer ======= -->
    <footer id="footer">
      <div class="footer-top">
        <div class="container">
          <div class="row justify-content-center">
            <div class="col-lg-6">
              <a href="#header" class="scrollto footer-logo"
                ><img src="assets/img/hero-logo.png" alt=""
              /></a>
              <h3>Against The Spread</h3>
              <p>
                All information used for entertainment purposes only. If you or
                someone you know may have an issue with gambling, contact
                1-800-GAM-BLER
              </p>
            </div>
          </div>
        </div>
      </div>
    </footer>
    <!-- End Footer -->
  </div>
</template>

<style></style>
