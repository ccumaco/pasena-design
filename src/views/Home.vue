<template>
  <div class="contenedor-imagen">
    <v-carousel :show-arrows="false" class="carrusel">
      <v-carousel-item
        class="imagenes"
        cover
        width="100%"
        v-for="(item, i) in fotos"
        :key="i"
        :src="item.src"
      >
        <div class="text-on-image">
          <v-img v-if="item.textTitleimg" width="200px" class="mb-4" :src="item.textTitleimg" />
          <h3 v-else :style="'color:' + item.colorText">{{item.textTitle}}</h3>
          <p :style="'color:' + item.colorText">{{ item.textDescription }}</p>
        </div>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
// @ is an alias to /src
import pruebaVista from "@/components/pruebaVista.vue";
// import navbarText from '@/components/navbarText.vue'

export default {
  name: "Home",
  components: {
    pruebaVista,
    // navbarText
  },
  data() {
    return {
      fotos: [
        {
          name: "foto1",
          src: require("./../assets/cerveza.png"),
          textTitle: "¿Cómo se elabora?",
          textDescription:
            "A lo largo de su historia, Paceña obtuvo más de 130 premios a la calidad a nivel mundial, otorgados por iTQI, Monde Selection y World Beer Cup. Estamos orgullosos de ser la cerveza más premiada de Bolivia.",
          colorText: '#000',
          textTitleimg: require("./../assets/¿Cómo se elabora_.png"),
        },
        {
          name: "foto2",
          src: require("./../assets/Foto_manos.png"),         
          textDescription:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras donec ornare odio orci quis at massa. At ornare enim duis maecenas et. Viverra ut ut sed pellentesque. Tincidunt ut tortor consectetur fringilla.",
          textTitleimg: require("./../assets/Nuestra-historia.png"),
          colorText: '#fff'
        },
        {
          name: "foto3",
          src: require("./../assets/glass-of-cold-beer-macro-photography.png"),
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.imagenes {
  .v-image.v-responsive.v-carousel__item.theme--dark {
    height: 100% !important;
  }
}
.carrusel {
  height: 100% !important;
  .v-carousel__controls{
    align-items: center;
    background: transparent;
    bottom: 0;
    display: flex;
    height: 100%;
    justify-content: center;
    list-style-type: none;
    position: absolute;
    width: 53px;
    z-index: 1;
    right: 20px !important;
    .v-item-group{
      button i{
        border-radius: 50%;
        border: 1px solid #000;
        color: transparent;
      }
      button.v-item--active{
        background-color: #fff;
      }
    }
  }
}
.drawer-derecho {
  background-color: red;
  height: 100%;
  width: 300px;
}
.contenedor-imagen {
  overflow: hidden;
  .imagen-lateral {
    height: 100%;
  }
}
.text-on-image {
  height: 300px;
  width: 350px;
  position: absolute;
  top: 300PX;
  right: 100px;
  z-index: 100;
  h3{
    font-size: 50px;
  }
  p{
    font-size: 20px;
  }
}
</style>
