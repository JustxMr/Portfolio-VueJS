<script setup> </script>

<template>
<section class="page_404">
  <div class="container">
    <div class="row">
      <div class="col-sm-12 ">
        <div class="col-sm-10 col-sm-offset-1  text-center">
          <div class="four_zero_four_bg">
            <h1 class="title_404">404</h1>

          </div>

          <div class="contant_box_404">
            <h3 class="title_second">
              On dirait que tu es perdu ...
            </h3>

            <p>La page que vous recherchez est introuvable !</p>

            <Router-Link to="/" class="link_404">Revenir a l'accueil</Router-Link>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<style scoped>
.page_404 {
  width: 100%;
  padding: 40px 0;
  background: #fff;
  font-family: "Arvo", serif;

}

.four_zero_four_bg {
  background-image: url(https://cdn.dribbble.com/users/285475/screenshots/2083086/dribbble_1.gif);
  height: 400px;
  background-position: center;
  background-repeat: no-repeat;
}

.four_zero_four_bg h1 {
  font-size: 80px;
}

.four_zero_four_bg h3 {
  font-size: 80px;
}

.link_404 {
  color: #fff !important;
  padding: 10px 20px;
  background: #39ac31;
  margin: 20px 0;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
}
.contant_box_404 {
  margin-top: -50px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.title_404 {
  text-align: center;
}
</style>