<template>
    <div>
      <b-carousel
       id="carousel"
       v-model="slide"
       :fade="true"
       :interval="2000"
       indicators
       @sliding-start="onSlideStart"
       @sliding-end="onSlideEnd"
     >
      <b-carousel-slide
          v-for="(carousel, i) in carousels"
          :key="i"
          class="carousel-item"
          :img-src="carousel.background_url"
          :text-html="carousel.text">
      </b-carousel-slide>
      <Logotipo class="logotipo" />
     </b-carousel>
   </div>
</template>

<script>
import Logotipo from '~/components/Global/DobankLogotipo'

export default {
    components: {
      Logotipo
    },

    data() {
      return {
        slide: 0,
        sliding: null,
        carousels: [
          {
            background_url: "https://i.imgur.com/2NBLT0B.png",
            text: "Faça portabilidade do seu salário para o <b> DoBank </b> e ganhe limite de crédito pré-aprovado." },
          {
            background_url: "https://i.imgur.com/m3lBKzJ.png",
            text: "Traga seus amigos para fazer parte do <b> DoBank </b> e ganhe bônus." },
          {
            background_url: "https://i.imgur.com/gM64w84.png",
            text: "Ganhos recorrentes, programa de afiliados, participações por resultados e premiações para empresários. E isso é só o começo." }
        ]
      }
    },

    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      }
    }
  }
</script>

<style>
.carousel-item {
  width: 100%;
  height: 78vh;
  background-color: black;
}
.carousel-indicators li {
  width: 0.55rem;
  height: 0.55rem;
  margin-bottom: 10px;
  text-indent: -999px;
  cursor: pointer;
  background-color: #fff;
  background-clip: padding-box;
  border: 0;
  border-radius: 10px;
  opacity: 1 !important;
}
.carousel-indicators .active {
  background-color: var(--default-color) !important;
}
.carousel-caption {
  left: 9%;
  right: 9%;
  margin: 40px auto;
  font-size: 0.82rem;
}
.carousel-item img {
  opacity: 0.675;
  filter: blur(0.01rem);
  -webkit-filter: blur(0.01rem);
}
</style>
