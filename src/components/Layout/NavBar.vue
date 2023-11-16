<template>
  <nav
    class="navbar is-warning has-shadow"
    role="navigation"
    aria-label="main navigation"
  >
    <div class="container is-max-desktop">
      <div class="navbar-brand">
        <RouterLink to="/" class="navbar-item">
          <img class="logo" src="/img/goat-logo.svg" />
        </RouterLink>

        <a
          role="button"
          class="navbar-burger is-clickable"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
          :class="{ 'is-active': showMobileNavBar }"
          @click="showMobileNavBar = !showMobileNavBar"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div
        id="navbarBasicExample"
        class="navbar-menu"
        :class="{ 'is-active': showMobileNavBar }"
      >
        <div class="navbar-start">
          <RouterLink to="/" class="navbar-item">Notas</RouterLink>
          <RouterLink to="stats" class="navbar-item">Datos</RouterLink>

          <div class="navbar-item has-dropdown is-hoverable">
            <a class="navbar-link"> Más </a>

            <div class="navbar-dropdown">
              <RouterLink to="/" class="navbar-item">Configuración</RouterLink>
              <hr class="navbar-divider" />
              <RouterLink to="/" class="navbar-item">Contacto</RouterLink>
            </div>
          </div>
        </div>

        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <RouterLink to="/signup" class="button is-primary is-clickable"
                >Registrarse</RouterLink
              >

              <RouterLink to="/signin" class="button is-light is-clickable"
                >Iniciar</RouterLink
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
/* 
    imports
*/
import { ref } from 'vue'

const showMobileNavBar = ref(false)
</script>

<style lang="css" scoped>
@media (max-width: 1023px) {
  .navbar-menu {
    position: absolute;
    left: 0;
    width: 100%;
  }
}
.logo {
  max-height: 3rem !important;
}
</style>
