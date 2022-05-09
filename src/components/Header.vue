<template>
  <header>
    <div class="container1">
      <router-link to="/acceuil">
        <img
          class="logo"
          src="../assets/logo2.png"
          alt="Logo de l'entreprise"
        />
      </router-link>
      <p><router-link to="/grossesse">Grossesse</router-link></p>
      <p><router-link to="/naissance">Naissance</router-link></p>
      <p><router-link to="/famille">Famille</router-link></p>
      <p><router-link to="/mariage">Mariage</router-link></p>
      <p><router-link to="/portrait">Portrait</router-link></p>
      <p><router-link to="/formulaire">Contact</router-link></p>
    </div>

    <div id="root">
      <div id="topnav" class="topnav">
        <a id="home_link" class="topnav_link" href="/#/acceuil"
          >VLD Photographe</a
        >

        <!-- Classic Menu -->
        <nav role="navigation" id="topnav_menu">
          <a class="topnav_link" href="/about">ABOUT</a>
          <a class="topnav_link" href="/contact-us">CONTACT</a>
        </nav>

        <a
          id="topnav_hamburger_icon"
          href="javascript:void(0);"
          @click.prevent="showResponsiveMenu()"
        >
          <!-- Some spans to act as a hamburger -->
          <span></span>
          <span></span>
          <span></span>
        </a>

        <!-- Responsive Menu -->
        <nav role="navigation" id="topnav_responsive_menu">
          <ul>
            <li><router-link to="/acceuil">Acceuil</router-link></li>
            <li>
              <router-link to="/grossesse">Grossesse</router-link>
            </li>
            <li><router-link to="/naissance">Naissance</router-link></li>
            <li><router-link to="/famille">Famille</router-link></li>
            <li><router-link to="/mariage">Mariage</router-link></li>
            <li><router-link to="/portrait">Portrait</router-link></li>
            <li><router-link to="/formulaire">Contact</router-link></li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",

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
a.router-link-exact-active.router-link-active {
  color: rgb(
    203,
    161,
    144
  ); /*permet de récupérer le lien active de chaque menu, permet de savoir dans quel menu on se trouve (ex: mariage, naissance...)*/
}

.container1 {
  /*contient tous le head*/
  /*background-color: burlywood;*/
  background-color: rgb(245, 245, 245);
  height: 165px; /*213*/
  display: flex;
  justify-content: space-around;
  border-radius: 10px 10px 0 0;
  /* box-shadow: 8px 5px 12px #555; */
}

.container1 img {
  width: 130px;
  padding-right: 170px;
}

.container1 a {
  /*contient les liens du head logo + texte*/
  text-decoration: none;
  color: black;
  font-size: 18px;
  // font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-family: "Barlow Semi Condensed", sans-serif;
}

.container1 p {
  /*le texte du head uniquement*/
  padding-top: 50px; /*70*/
  transition: transform 0.4s;
}

.container1 p:hover {
  transform: scale(1.08);
}

.container1 a:hover {
  color: rgb(203, 161, 144);
}

#root {
  /*pour la partie PC on retir le menu hamburger*/
  display: none;
}

@media only screen and (max-width: 905px) {
  #root {
    /*affichage du menu burger*/
    display: block;
  }

  .container1 {
    /*on enlève la bar de navigation classique*/
    display: none;
  }

  /* ******************** NAV BAR ******************** */
  .topnav {
    /*background-color: #333;*/
    background-color: rgb(245, 245, 245);
    display: flex;
    align-items: center;
    width: 100%;
    border-radius: 10px 10px 0 0;
    // box-shadow: 8px 5px 12px #555;
  }
  .topnav_link {
    color: rgb(203, 161, 144);
    padding: 12px;
    text-decoration: none;
  }
  .topnav_link:hover {
    color: #0078b4;
  }

  /* hide responsive menu */
  #topnav_hamburger_icon,
  #topnav_responsive_menu {
    display: none;
  }

  /* hide classic menu */
  #topnav_menu {
    display: none;
  }

  /* position home link at left and hamburger at right */
  #home_link {
    flex-grow: 1;
  }

  /* disable horizontal scrolling  */
  #root {
    position: relative;
    overflow-x: hidden; //barre de défilement horizontale
    overflow-y: hidden;
  }

  /* show responsive menu and position at the right of the screen */
  #topnav_responsive_menu {
    display: block;
    position: absolute;
    margin: 0;
    right: 0;
    top: 0;
    width: 100vw;
    height: 100vh;

    z-index: 99;

    transform-origin: 0% 0%;
    transform: translate(200%, 0);

    transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
  }

  #topnav_responsive_menu ul {
    display: flex;
    flex-direction: column;

    position: absolute;
    margin: 0;
    right: 0;
    top: 0;

    min-width: 50vw;
    height: 100vh;
    padding: 56px 0 0;

    text-align: center;

    background: #ededed;
    list-style-type: none;
    -webkit-font-smoothing: antialiased;
  }

  #topnav_responsive_menu li {
    padding: 12px 24px;
  }

  #topnav_responsive_menu a {
    white-space: nowrap;
    color: #333;
    text-decoration: none;
  }

  /* And let's slide it in from the right */
  #topnav_responsive_menu.open {
    transform: none;
    position: fixed;
  }

  /* ******************** HAMBURGER ICON ******************** */
  /* define size and position of the hamburger link */
  #topnav_hamburger_icon {
    display: block;
    position: relative;
    margin: 16px;
    width: 33px;
    height: 28px;

    z-index: 100;

    -webkit-user-select: none;
    user-select: none;
    cursor: pointer;
  }

  /* define the style (size, color, position, animation, ...) of the 3 spans */
  #topnav_hamburger_icon span {
    display: block;
    position: absolute;
    height: 4px;
    width: 100%;
    margin-bottom: 5px;

    background: #ededed;
    border-radius: 3px;

    z-index: 100;

    opacity: 1;
    left: 0;

    -webkit-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
    -webkit-transition: 0.25s ease-in-out;
    -moz-transition: 0.25s ease-in-out;
    -o-transition: 0.25s ease-in-out;
    transition: 0.25s ease-in-out;
  }

  /* set the 3 spans position to look like a hamburger */
  #topnav_hamburger_icon span:nth-child(1) {
    top: 0px;
    -webkit-transform-origin: left top;
    -moz-transform-origin: left top;
    -o-transform-origin: left top;
    transform-origin: left top;
  }
  #topnav_hamburger_icon span:nth-child(2) {
    top: 12px;
    -webkit-transform-origin: left center;
    -moz-transform-origin: left center;
    -o-transform-origin: left center;
    transform-origin: left center;
  }
  #topnav_hamburger_icon span:nth-child(3) {
    top: 24px;
    -webkit-transform-origin: left bottom;
    -moz-transform-origin: left bottom;
    -o-transform-origin: left bottom;
    transform-origin: left bottom;
  }

  /* change color when opening the menu */
  #topnav_hamburger_icon.open span {
    background: #333;
  }

  /* the first span rotates 45° \ */
  #topnav_hamburger_icon.open span:nth-child(1) {
    width: 110%;
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    transform: rotate(45deg);
  }

  /* the second span disappears */
  #topnav_hamburger_icon.open span:nth-child(2) {
    width: 0%;
    opacity: 0;
  }

  /* the last span rotates -45° / */
  #topnav_hamburger_icon.open span:nth-child(3) {
    width: 110%;
    -webkit-transform: rotate(-45deg);
    -moz-transform: rotate(-45deg);
    -o-transform: rotate(-45deg);
    transform: rotate(-45deg);
  }

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
