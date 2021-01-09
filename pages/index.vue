<template>
  <section>
    <Carousel />
    <b-button class="b-button default-color my-4">Abra a sua conta!</b-button>
    <p class="p-login">
      Já tem conta? <a href="#">Entre aqui!</a>
    </p>
  </section>
</template>

<script>
import Carousel from '~/components/Walkthrough/Carousel'

export default {
  components: {
    Carousel
  }
}
</script>

<style>
.p-login {
  text-align: center;
  font-size: 0.878rem;
}
.p-login a {
  color: var(--default-color);
}
</style>
