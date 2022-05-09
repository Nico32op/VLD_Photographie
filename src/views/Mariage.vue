<template>
  <div class="mariage">
    <head>
      <meta charset="utf-8" />

      <link
        href="https://fonts.googleapis.com/css?family=Raleway:600,900"
        rel="stylesheet"
      />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Projet Valou</title>
    </head>
    <Header />

    <p class="heading">Mariages</p>
    <div class="texte">
      <p>
        Si vous êtes sur cette page, tout d’abord, mes plus sincères
        félicitations ! Elle ou il a dit oui et cette réponse marque le début
        d’une merveilleuse aventure ! Au milieu de tous les préparatifs, vous
        devez choisir celui ou celle qui aura le privilège d’immortaliser cette
        merveilleuse journée, le/la photographe (en l’occurrence-moi si vous
        êtes en train de me lire 😜).
      </p>

      <p>
        Mon calendrier 2022 est ici (lien vers un calendrier avec les dates
        dispo) Si votre date est dispo alors filez vers la page
        <router-link to="/formulaire">contact</router-link> pour m’écrire est
        réserver votre date. Je vous contacterais alors le plus rapidement
        possible pour programmer d’une rencontre et ainsi discuter ensemble de
        ce jour si particulier. Et autour d’un café ou un thé c’est toujours
        mieux non ? Voici tout de même un premier aperçu des tarifs proposés.
      </p>
    </div>

    <div class="vueGallery">
      <!-- partie diapo -->
      <div
        class="activePhoto"
        :style="'background-image: url(' + photos[activePhoto] + ');'"
      >
        <button
          type="button"
          aria-label="Previous Photo"
          class="previous"
          @click="previousPhoto()"
        >
          <i class="fas fa-chevron-circle-left"></i>
        </button>
        <button
          type="button"
          aria-label="Next Photo"
          class="next"
          @click="nextPhoto()"
        >
          <i class="fas fa-chevron-circle-right"></i>
        </button>
      </div>
      <div class="thumbnails">
        <div
          v-for="(photo, index) in photos"
          :src="photo"
          :key="index"
          @click="activePhoto = index"
          :class="{ active: activePhoto == index }"
          :style="'background-image: url(' + photo + ')'"
        ></div>
      </div>
    </div>

    <div class="gallery-image">
      <div class="img-box">
        <img src="https://picsum.photos/350/250?image=444" alt="" />
        <div class="transparent-box">
          <div class="caption">
            <p>Library</p>
            <p class="opacity-low">Architect Design</p>
          </div>
        </div>
      </div>
      <div class="img-box">
        <img src="https://picsum.photos/350/250/?image=232" alt="" />
        <div class="transparent-box">
          <div class="caption">
            <p>Night Sky</p>
            <p class="opacity-low">Cinematic</p>
          </div>
        </div>
      </div>
      <div class="img-box">
        <img src="https://picsum.photos/350/250/?image=431" alt="" />
        <div class="transparent-box">
          <div class="caption">
            <p>Tea Talk</p>
            <p class="opacity-low">Composite</p>
          </div>
        </div>
      </div>
      <div class="img-box">
        <img src="images/logo2.png" alt="" />
        <div class="transparent-box">
          <div class="caption">
            <p>Road</p>
            <p class="opacity-low">Landscape</p>
          </div>
        </div>
      </div>
      <div class="img-box">
        <img src="https://picsum.photos/350/250?image=344" alt="" />
        <div class="transparent-box">
          <div class="caption">
            <p>Sea</p>
            <p class="opacity-low">Cityscape</p>
          </div>
        </div>
      </div>
      <div class="img-box">
        <img src="https://picsum.photos/350/250?image=494" alt="" />
        <div class="transparent-box">
          <div class="caption">
            <p>Vintage</p>
            <p class="opacity-low">Cinematic</p>
          </div>
        </div>
      </div>

      <div class="img-box">
        <img
          src="https://picsum.photos/350/250?image=494"
          alt="Image de la page d'acceuil du site d'informations"
        />
        <div class="transparent-box" onclick="">
          <div class="caption">
            <p>Collection AFFETTO</p>
            <p class="opacity-low">
              Rendez-vous préalable pour organisation de la journée <br /><br />
              Préparatifs des mariés<br /><br />
              Cérémonie Civil et/ou Religieuse <br /><br />
              Photos de couple <br /><br />
              50 fichiers numériques H
            </p>
          </div>
        </div>
      </div>

      <div class="img-box">
        <img
          src="https://picsum.photos/350/250?image=344"
          alt="Image de la page d'acceuil du site d'informations"
        />
        <div class="transparent-box" onclick="">
          <div class="caption">
            <p>Collection TENEREZZA</p>
            <p class="opacity-low">
              Rendez-vous préalable pour organisation de la journée <br /><br />

              Préparatifs des mariés <br /><br />

              Cérémonie Civil et/ou Religieuse <br /><br />

              Photos de couple<br /><br />

              Vin d’honneur <br /><br />

              80 fichiers numériques HD
            </p>
          </div>
        </div>
      </div>

      <div class="img-box">
        <img
          src="https://picsum.photos/350/250/?image=431"
          alt="Image de la page d'acceuil du site d'informations"
        />
        <div class="transparent-box" onclick="">
          <div class="caption">
            <p>Collection AMORE</p>
            <p class="opacity-low">
              Rendez-vous préalable pour organisation de la journée<br /><br />
              Préparatifs des mariés<br /><br />
              Cérémonie Civil et/ou Religieuse<br /><br />
              Photos de couple<br /><br />
              Vin d’honneur<br /><br />
              Soirée jusqu’à la pièce montée<br /><br />
              L’ensemble des fichiersnumérique HD
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="card2">
      <!--permet de mettre les card les une à coté des autres -->
      <Card
        titre="Collection AFFETTO"
        description="📷 Rendez-vous préalable pour organisation de la journée"
        description2="📷 Préparatifs des mariés"
        description3="📷 Cérémonie Civil et/ou Religieuse"
        description4="📷 Photos de couple"
        description5="📷 50 fichiers numériques H"
        prix="550€"
      />
      <Card
        titre="Collection TENEREZZA"
        description="📷 Rendez-vous préalable pour organisation de la journée"
        description2="📷 Préparatifs des mariés"
        description3="📷  Cérémonie Civil et/ou Religieuse"
        description4="📷  Photos de couple"
        description5="📷  Vin d’honneur"
        description6="📷 80 fichiers numériques HD"
        prix="780€"
      />

      <Card
        titre="Collection AMORE"
        description="📷 Rendez-vous pour organiser la journée"
        description2="📷 Préparatifs des mariés"
        description3="📷 Cérémonie Civil et/ou Religieuse"
        description4="📷 Photos de couple"
        description5="📷 Vin d’honneur"
        description6="📷 Soirée jusqu’à la pièce montée"
        description7="📷 L’ensemble des fichiers numérique HD"
        prix="990€"
      />
    </div>

    <Footer />
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";
import Header from "@/components/Header.vue";
import Card from "@/components/Card.vue";
export default {
  name: "Mariage",
  components: { Footer, Header, Card },
  data() {
    return {
      photos: [
        require("../assets/coeur.jpg"), //require permet de créer l'url de l'image
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-02-min.jpg",
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-03-min.jpg",
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-04-min.jpg",
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-05-min.jpg",
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-06-min.jpg",
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-07-min.jpg",
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/20625/lordea-home-08-min.jpg",
        "http://localhost:8080/img/mariage_maria.98d7da59.jpg",
        require("../assets/bapteme_tina.jpg"),
      ],
      activePhoto: "",
    };
  },
  mounted() {
    this.activePhoto = 0;
    document.addEventListener("keydown", (event) => {
      if (event.which == 37) this.previousPhoto();
      if (event.which == 39) this.nextPhoto();
    });
  },
  methods: {
    nextPhoto() {
      this.activePhoto =
        this.activePhoto + 1 < this.photos.length ? this.activePhoto + 1 : 0;
    },
    previousPhoto() {
      this.activePhoto =
        this.activePhoto - 1 >= 0
          ? this.activePhoto - 1
          : this.photos.length - 1;
    },
  },
};
</script>

<style lang="scss">
body {
  font-family: Raleway;
  /*background-color: #202125;*/
  background-color: white;
}

.heading {
  /*partie titre des rubriques + son animation */
  text-align: center;
  font-size: 2em;
  letter-spacing: 1px;
  padding: 0px;
  color: black;
  background: linear-gradient(
    to right,
    rgb(0, 0, 0),
    rgb(0, 0, 0),
    rgb(0, 0, 0),
    rgb(0, 0, 0),
    rgba(0, 0, 0, 0)
  );
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: h1anim 4s linear forwards;
  background-size: 500% auto;
  display: inline-block;
  background-position: 150% center;
  background-repeat: no-repeat;
  margin: 10px;
}

@keyframes h1anim {
  from {
    background-position: 150% center;
  }
  to {
    background-position: 0 center;
  }
} /*fin partie titre rubrique + son animation */

.texte a {
  font-size: 18px;
  text-decoration: underline;
  font-weight: bold;
}

.texte {
  /*texte au dessus des photo de l'acceuil + animation*/
  margin: auto;
  width: 70%;
  padding-top: 0px;
  font-family: "GFS Didot", serif;
  text-align: justify;
  font-size: 18px;
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

.mariage .gallery-image {
  display: none;
}

$brand: #5c4084; //partie diapo

.vueGallery {
  background-color: #f5f5f5;
  .activePhoto {
    width: 100%;
    margin-bottom: 5px;
    padding-bottom: 65%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    border: 2px solid #fff;
    position: relative;

    button {
      border: none;
      background-color: transparent;
      font-size: 32px;
      color: #fff;
      opacity: 0.5;
      position: absolute;
      outline: none;
      height: 100%;

      &:hover {
        opacity: 1;
      }
      &.previous {
        padding: 0 1em 0 0.7em;
        left: 0;
        background: -moz-linear-gradient(
          left,
          rgba(0, 0, 0, 0.5) 0%,
          rgba(0, 0, 0, 0) 100%
        );
        background: -webkit-linear-gradient(
          left,
          rgba(0, 0, 0, 0.5) 0%,
          rgba(0, 0, 0, 0) 100%
        );
        background: linear-gradient(
          to right,
          rgba(0, 0, 0, 0.5) 0%,
          rgba(0, 0, 0, 0) 100%
        );
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#80000000', endColorstr='#00000000',GradientType=1 );
      }
      &.next {
        padding: 0 0.7em 0 1em;
        right: 0;
        background: -moz-linear-gradient(
          left,
          rgba(0, 0, 0, 0) 0%,
          rgba(0, 0, 0, 0.5) 100%
        );
        background: -webkit-linear-gradient(
          left,
          rgba(0, 0, 0, 0) 0%,
          rgba(0, 0, 0, 0.5) 100%
        );
        background: linear-gradient(
          to right,
          rgba(0, 0, 0, 0) 0%,
          rgba(0, 0, 0, 0.5) 100%
        );
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#00000000', endColorstr='#80000000',GradientType=1 );
      }
    }
  }
  .thumbnails {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
    grid-gap: 5px;

    div {
      width: 100%;
      border: 2px solid #fff;
      outline: 2px solid #fff;
      cursor: pointer;
      padding-bottom: 65%;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      opacity: 1;

      &:hover {
        opacity: 0.6;
      }
      &.active {
        outline-color: $brand;
        opacity: 1;
      }
    }
  }
} //fin diapo

.card2 {
  //contient l'ensemble des cards
  display: flex;
  justify-content: space-around;
}

@media only screen and (max-width: 975px) {
  .vueGallery {
    display: none;
  }
  .mariage .gallery-image {
    padding: 0px;
    display: block;
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

  .card2 {
    //contient l'ensemble des cards
    flex-direction: column;
  }
}
</style>
