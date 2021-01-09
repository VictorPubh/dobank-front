<template>
  <div class="element white">
    <h1 class="form-title white medium py2 pb0"> Tudo certo! </h1>
    <b-form>
      <b-form-group
        id="input-group"
        label="Qual é o seu nome completo?"
        description="Digite o seu nome de registro (como está no documento)"
        label-for="input-name">
        <b-form-input
          id="input"
          v-model="name"
          type="text"
          placeholder="Insira o seu nome"
          required>
        </b-form-input>
      </b-form-group>
      <b-button @click="setName(name)" class="b-button reverse-default-color gray my-3">Próximo</b-button>
    </b-form>
</div>
</template>

<script>
  export default {
    data() {
      return {
        name: ''
      }
    },
    methods: {
      setName(name) {
        this.$emit("setName", { name })
      }
    }
  }
</script>
