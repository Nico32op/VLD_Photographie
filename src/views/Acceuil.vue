<template>
  <div class="acceuil">
    <head>
      <meta charset="utf-8" />

      <link rel="preconnect" href="https://fonts.googleapis.com" />
      <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
      <link
        href="https://fonts.googleapis.com/css2?family=GFS+Didot&display=swap"
        rel="stylesheet"
      />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Projet Valou</title>
    </head>
    <Header />

    <div class="texte">
      <p>
        « Photographier c’est mettre sur la même ligne de mire la tête, l’œil et
        le cœur » Henri Cartier Bresson<br />

        Photographe diplômée, laissez-moi capturer les plus beaux moments de
        votre vie.
      </p>
    </div>

    <div class="gallery-image">
      <div class="img-box">
        <router-link to="/mariage">
          <img class="o" src="../assets/mariage_maria.jpg" />
          <div class="transparent-box">
            <div class="caption">
              <p>Mariage</p>
              <p class="opacity-low">Architect Design</p>
            </div>
          </div>
        </router-link>
      </div>
      <div class="img-box">
        <router-link to="/portrait">
          <img class="o" src="../assets/logo2.png" />
          <div class="transparent-box">
            <div class="caption">
              <p>Portrait</p>
              <p class="opacity-low">Architect Design</p>
            </div>
          </div>
        </router-link>
      </div>
      <div class="img-box">
        <router-link to="/naissance">
          <img class="o" src="../assets/coeur.jpg" />
          <div class="transparent-box">
            <div class="caption">
              <p>Naissance</p>
              <p class="opacity-low">Architect Design</p>
            </div>
          </div>
        </router-link>
      </div>
      <div class="img-box">
        <router-link to="/famille">
          <img class="o" src="../assets/bapteme_tina.jpg" />
          <div class="transparent-box">
            <div class="caption">
              <p>Famille</p>
              <p class="opacity-low">Architect Design</p>
            </div>
          </div>
        </router-link>
      </div>
      <div class="img-box">
        <router-link to="/grossesse">
          <img class="o" src="../assets/logo2.png" />
          <div class="transparent-box">
            <div class="caption">
              <p>Grossesse</p>
              <p class="opacity-low">Architect Design</p>
            </div>
          </div>
        </router-link>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Acceuil",
  components: { Header, Footer },
  methods: {
    showResponsiveMenu() {
      var menu = document.getElementById("topnav_responsive_menu");
      var icon = document.getElementById("topnav_hamburger_icon");
      var root = document.getElementById("root");
      if (menu.className === "") {
        menu.className = "open";
        icon.className = "open";
        root.style.overflowY = "hidden";
      } else {
        menu.className = "";
        icon.className = "";
        root.style.overflowY = "";
      }
    },
  },
};
</script>

<style lang="scss">
/*PARTIE ACCUEIL*/
p:focus /* Quand le visiteur sélectionne le lien */ {
  background-color: #ffcc66;
}

.texte {
  /*texte au dessus des photo de l'acceuil + animation*/
  margin: auto;
  width: 50%;
  padding-top: 30px;
  font-family: "GFS Didot", serif;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.texte {
  opacity: 0; /* make things invisible upon start */
  animation: fadeIn ease-in 1;
  animation-fill-mode: forwards;
  animation-duration: 1.8s;
}

/*PARTIE GALLERY*/

.gallery {
  padding: 20px;
  /* border: 2px solid #ababab;
    border-radius: 20px; */
  width: 460px;
  display: grid;
  gap: 5px;
  grid-template-columns: 150px 150px 150px;
  grid-template-rows: 150px 150px 150px;
  grid-auto-flow: dense;
  margin: auto;
}

.image {
  height: 100%;
  width: 100%;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 100%;
  filter: grayscale(100%) opacity(0.5);
  transition: 0.25s ease-out;
}

.image.tall {
  grid-area: span 2 / auto;
}

.image.wide {
  grid-area: auto / span 2;
}

.image:hover {
  filter: grayscale(0%) opacity(1);
  background-size: 135%;
}

/* @keyframes slidy {
    0% { left: 0%; }
    20% { left: 0%; }
    25% { left: -100%; }
    45% { left: -100%; }
    50% { left: -200%; }
    70% { left: -200%; }
    75% { left: -300%; }
    95% { left: -300%; }
    100% { left: -400%; }
    }
    
    body { margin: 0; } 
    div#slider { overflow: hidden; }
    div#slider figure img { width: 20%; float: left; }
    div#slider figure { 
      position: relative;
      width: 500%;
      margin: 0;
      left: 0;
      text-align: left;
      font-size: 0;
      animation: 20s slidy infinite; 
    } */

/*PARTIE AUTRES PAGES : mariages, grossesses..*/

body {
  font-family: optima;
  /*background-color: #202125;*/
  background-color: white;
}

.heading {
  text-align: center;
  font-size: 2em;
  letter-spacing: 1px;
  padding: 0px;
  color: black;
}

.gallery-image {
  padding: 0px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.gallery-image img {
  height: 280px;
  width: 350px;
  transform: scale(1);
  transition: transform 0.4s ease;
}

.img-box {
  box-sizing: content-box;
  margin: 10px;
  height: 280px;
  width: 350px;
  overflow: hidden;
  display: inline-block;
  color: white;
  position: relative;
  background-color: white;
}

.img-box p {
  color: white;
}

.caption {
  position: absolute;
  bottom: 1px;
  left: 20px;
  opacity: 0;
  transition: transform 0.3s ease, opacity 0.3s ease;
}

.transparent-box {
  height: 280px;
  width: 350px;
  background-color: rgba(0, 0, 0, 0);
  position: absolute;
  top: 0;
  left: 0;
  transition: background-color 0.3s ease;
}

.img-box:hover img {
  transform: scale(1.1);
}

.img-box:hover .transparent-box {
  background-color: rgba(0, 0, 0, 0.5);
}

.img-box:hover .caption {
  transform: translateY(-20px);
  opacity: 1;
}

.img-box:hover {
  cursor: pointer;
}

.caption > p:nth-child(2) {
  font-size: 0.8em;
}

.opacity-low {
  opacity: 0.5;
}

.gallery1 img {
  height: 240px;
  width: 441px;
  -moz-transition: opacity 0.9s;
  -webkit-transition: opacity 0.9s;
  -o-transition: opacity 0.9s;
}

.gallery1 img:hover {
  opacity: 0.5;
  -moz-transition: opacity 0.7s;
  -webkit-transition: opacity 0.7s;
  -o-transition: opacity 0.7s;
}
@media only screen and (max-width: 900px) {
  .gallery {
    /* border: 2px solid #ababab;
        border-radius: 20px; */
    width: 100%;
    display: grid;
    gap: 5px;
    grid-template-columns: 100px 100px 100px;
    grid-template-rows: 100px 100px 100px;
    grid-auto-flow: dense;
    margin: auto;
  }
}
</style>
