<template>
  <div class="element white">
    <h1 class="form-title white medium py2 pb0"> Hey! </h1>
    <p class="text white is-center px4 py2">
      Vamos precisar de algumas informações pra abrir a sua conta dobank. </p>
    <b-form>
      <b-form-group
        id="input-group"
        :label="`Pra começar, informe seu ${term}:`"
        label-for="input-federalId">
        <b-form-input
          id="input"
          v-model="federalId"
          type="text"
          v-mask="['###.###.###-##', '##.###.###/####-##']"
          :placeholder="`Insira o ${term}`"
          required>
        </b-form-input>
      </b-form-group>
      <b-button @click="setFederalId(federalId)" class="b-button reverse-default-color gray my-3">Próximo</b-button>
    </b-form>
</div>
</template>

<script>
  export default {
    data() {
      return {
        federalId: ''
      }
    },

    props: {
      federalIdType: {
        type: String,
        default: 'personal'
      },
      term: {
        type: String,
        default: 'CPF'
      }
    },

    methods: {
      setFederalId(federalId) {
        this.$emit("setFederalId", { federalId })
      }
    }
  }
</script>
