<script>
	import Booking from './Booking.svelte';

</script>

<style>
  .bg {
    background: rgb(63, 81, 181);

    /* Full height */
    height: 400px;

    /* Center and scale the image nicely */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }

  .mdl-navigation a {
    color: rgb(63, 81, 181) !important;
  }

  .bg-small {
    background: rgb(63, 81, 181);

    /* Full height */
    height: 200px;

    /* Center and scale the image nicely */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }

  .container {
    max-width: 1180px;
    margin: 0 auto;
  }
  .text {
    vertical-align: middle;
    text-align: center;
    color: rgb(255, 255, 255);
  }

  .rounded {
    border-radius: 5px;
  }

  .layout-header {
    padding-bottom: 30px;
    padding-right: 10px;
    color: rgb(255, 255, 255);
    font-size: 12px;
    text-align: right;
  }
</style>


<div
  class="mdl-layout mdl-js-layout mdl-layout--fixed-header
  mdl-layout--fixed-tabs">
  <header class="mdl-layout__header">
    <div class="mdl-layout__header-row">
      <!-- Title -->
    </div>
    <!-- Tabs -->
    <div class="mdl-layout__tab-bar mdl-js-ripple-effect">
      <a href="#fixed-tab-1" class="mdl-layout__tab is-active">Home</a>
      <a href="#fixed-tab-2" class="mdl-layout__tab">Map</a>
      <a href="#fixed-tab-3" class="mdl-layout__tab">Taxi</a>
    </div>
  </header>
  <div class="mdl-layout__drawer">
    <span
      class="mdl-layout-title layout-header white"
      style="background-color: rgb(63,81,181)">
      28°|Friday, October 25, 2019
    </span>
    <nav class="mdl-navigation">
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-home" />
        Home
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-plane" />
        Traveller Guide
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-book" />
        At the Airport
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-plane-departure" />
        To & From The Airport
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-bed" />
        Oryx Airport Hotel
      </a>
      <hr />
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-shopping-cart" />
        Shop
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-utensils" />
        Dine
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-couch" />
        Relax
      </a>
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-bell" />
        Facilities & Services
      </a>
      <hr />
      <a class="mdl-navigation__link" href="">
        <i class="fas fa-cog" />
        Settings
      </a>
    </nav>
  </div>

  <main class="mdl-layout__content">
    <section class="mdl-layout__tab-panel is-active" id="fixed-tab-1">
      <div class="page-content">
        <section
          class="bg mdl-cell mdl-cell--12-col rounded"
          style="background-image: url(public/images/airport.jpg);" />
        <section class="container">
          <div class="mdl-grid">
            <div
              class="bg-small mdl-cell mdl-cell--4-col rounded"
              style="background-image: url(images/shopping.jpg);">
              <div>
                <h4 class="title text">Shop</h4>
              </div>
            </div>
            <div
              class="bg-small mdl-cell mdl-cell--4-col rounded"
              style="background-image: url(images/dine.jpg)">
              <div>
                <h4 class="title text">Dine</h4>
              </div>
            </div>
            <div
              class="bg-small mdl-cell mdl-cell--4-col rounded"
              style="background-image: url(images/relax.jpg);">
              <div>
                <h4 class="title text">Relax</h4>
              </div>
            </div>
          </div>
          <div class="mdl-grid">
            <div
              class="bg-small mdl-cell mdl-cell--8-col rounded"
              style="background-image: url(images/explore.jpg);">
              <div>
                <h4 class="title text">Explore HIA</h4>
              </div>
            </div>
            <div
              class="bg-small mdl-cell mdl-cell--4-col rounded"
              style="background-image: url(images/scan.jpg);">
              <div>
                <h4 class="title text">Scan</h4>
              </div>
            </div>
          </div>
        </section>
      </div>
    </section>
    <section class="mdl-layout__tab-panel" id="fixed-tab-2">
      <div class="page-content">
        <!-- Your content goes here -->
        <section class="container">
          <img src="images/map.PNG" alt="" />
        </section>
      </div>
    </section>
    <section class="mdl-layout__tab-panel" id="fixed-tab-3">
      <div class="page-content">
        <!-- Your content goes here -->
				<Booking></Booking>
      </div>
    </section>
  </main>
</div>
