<template>
    <v-navigation-drawer
      class="accent-4 navigation-component"
      dark
      permanent
    >
      <v-list>
        <v-list-item class="logo-navbar">
          <v-img cover src="./../assets/Grupo-836.png" alt="" />
        </v-list-item>
        <v-list-item
          v-for="(item,index) in items"
          :key="index"
          link
        >
          <v-list-item-content>
            <v-list-item-title class="name-categories">
                <router-link class="router" :to="item.route">
                  {{ item.name }}
                </router-link>
              </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="footer-navbar">
          <div class="border-iconuser">
           <i class="far fa-user"></i>
          </div>
          <span class="registro">Registro</span>
          <div class="icon-container">
          <i class="fab fa-instagram"></i>
          <i class="fab fa-facebook"></i>
          <i class="fab fa-youtube"></i>
          <i class="fab fa-twitter"></i>
          </div>
        </div>
      </v-list>
    </v-navigation-drawer>
</template>


<script>
  export default {
    name: 'navbarSecond',
    data () {
      return {
        items: [
          {name: 'Inicio', route: '/'},
          {name: 'Historia', route: '/historia'},
          {name: 'Nuestra Cerveza', route: '/nuestraCerveza'},
          {name: 'Experiencia Bolivia', route: '/experiencia'},
          {name: 'Modelos de mujer', route: '/modelos'},
          {name: 'Compras', route: '/compras'},
        ]
      }
    }
  }
</script>
<style lang="scss">
@import '../styles/styles.scss';
</style>
