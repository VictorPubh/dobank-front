<template>
  <div class="component white">
    <h1 class="form-title white medium py2 pb0"> Estamos quase lá! </h1>
    <b-form>
      <b-form-group
        id="input-group"
        label="Qual é o seu e-mail?"
        description="Vamos te enviar um código para confirmação."
        label-for="input-email">
        <b-form-input
          id="input"
          v-model="email"
          type="email"
          placeholder="Insira seu e-mail"
          required>
        </b-form-input>
      </b-form-group>
      <b-button @click="setEmail(email)" class="b-button reverse-default-color my-3">Próximo</b-button>
    </b-form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        email: ''
      }
    },
    methods: {
      setEmail(email) {
        this.$emit("setEmail", { email })
      }
    }
  }
</script>
