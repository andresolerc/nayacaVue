<template>

        <b-nav toggleable type="light" variant="light" class="navbar navbar-expand-sm navbar-dark bg-transparent" id="navmain">
              <router-link to="/" class="navbar-brand"><span id="nayacalogo">
                      <img src="../assets/media/nayaca-white-logo.png" alt="Nayaca"></span>
              </router-link>

              <b-navbar-toggle target="navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation"/>
               <b-collapse is-nav id="navbarSupportedContent">
                     <b-navbar-nav>
                                <router-link to="/resume" class="nav-link nav-item" id="navlink_1">Resume</router-link>
                                <router-link to="/blog" class="nav-link nav-item" id="navlink_2">Blog</router-link>
                     </b-navbar-nav>
               </b-collapse>
         </b-nav>

</template>

<script>
export default {
  name: 'TheNavbar',
  components: {

  }
}
</script>

<style>

#navmain {
    position: fixed;
    z-index: 5;
}

#navlink_1, #navlink_2 {
  color: white;
  font-size: 0.75em;
  text-align: left;


}
#navlink_1:hover, #navlink_2:hover {
  color: #FF6F61;
}

.navbar {
  top: 0;
  left: 0;
  width: 100%;
}

.navbar-dark .navbar-toggler-icon {
  background-image: url("../assets/media/burgericon.png");
}



.navbar-brand img {
  width: 50px;
  height: 50px;
}

.navbar-toggler, .navbar-toggler:hover, .navbar-toggler:active {
  border: none;
  padding: 0;
  margin: 0;
  outline: none;
}

.nav-item img {
  color: #FF6F61 !important;
  padding-right: 10px;
}

@media (min-width: 576px) {
  .nav-item a {
    padding-top: 28px;
  }
  #navlink_1, #navlink_2 {
    margin-top: 18px;
  }
}

@media (min-width: 1024px) {

  .navbar-brand img {
    width: 75px;
    height: 75px;
  }
  #navlink_1, #navlink_2 {
    font-size: 1em;
    margin-top: 26px;
  }
  .navbar-expand-sm .nav-item a {
    padding-top: 36px;
  }
}

@media (min-width: 1350px) {

  .navbar-brand img {
    width: 100px;
    height: 100px;
  }
  #navlink_1, #navlink_2 {
    font-size: 1.25em;
    margin-top: 35px;
  }
  .navbar-expand-sm .nav-item a {
    padding-top: 43px;
  }
}
</style>
