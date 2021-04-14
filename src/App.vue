<template>
  <v-app>
    <v-main>
      <div class="contenedor">
        <navbarSecond class="vistas" />
        <Home class="vistas" />
        <v-navigation-drawer
          class="navegation"
          v-model="drawer"
          absolute
          temporary
          overlay-opacity="0"
          right
        >
          <div class="contenido">
            <h2>NUESTRA HISTORIA</h2>
            <p>
              Nuestra historia se puede simplificar en dos palabras: tradición y
              calidad. Desde hace 135 años estamos para celebrar el orgullo
              boliviano.
            </p>
            <div class="content-btn">
              <v-btn class="boton-close" @click="drawer = !drawer"
                >CONOCE MAS</v-btn
              >
            </div>
          </div>
        </v-navigation-drawer>
      </div>
      <v-footer >
        <div class="footer"></div>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script>
import navbarSecond from "./components/navbarSecond";
import Home from "./views/Home";

export default {
  name: "App",

  components: {
    navbarSecond,
    Home,
  },

  data: () => ({
    drawer: true,
  }),
};
</script>
<style lang="scss">
$primary-color: #e2231a;
$second-color: #fff;
* {
  margin: 0;
  padding: 0;
}
.row-app {
  height:100%;
}
.cols {
  margin: 0;
  padding: 0 !important;
}
.contenedor {
  height: 100%;
  display: flex;
  .vistas {
    display: inline-block;
  }
}
.navegation {
  padding: 105px;
  color: $second-color;
  width: 400px !important;
  background-color: $primary-color !important;
  .v-navigation-drawer__content {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .contenido {
    h2 {
      font-size: 36px;
    }
    p {
      font-size: 10px;
    }
    .content-btn {
      width: 100%;
      text-align: center;
      .boton-close {
        width: 100%;
        margin: 0 auto;
        color: $second-color !important;
        background-color: transparent !important;
        border-radius: 50px !important;
        border: 1px solid $second-color;
      }
    }
  }
}
.footer{
  position: absolute;
  bottom: 0;
  height: 32px;
  background-color: #0f446e;
  z-index: 1000;
  width: 100%;
  left: 0;
}
</style>
