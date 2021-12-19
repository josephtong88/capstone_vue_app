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
              <h3>Knight</h3>
              <p>
                Et aut eum quis fuga eos sunt ipsa nihil. Labore corporis magni
                eligendi fuga maxime saepe commodi placeat.
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
