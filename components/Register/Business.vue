<template>
  <div class="element white">
    <h1 class="form-title white medium py2 pb0"> Olá, {{ peopleName }} </h1>
    <b-form>
      <b-form-group
        id="input-group"
        label="Qual é o nome da empresa?"
        description="Pode ser o nome fantasia."
        label-for="input-name">
        <b-form-input
          id="input"
          v-model="businessName"
          type="text"
          placeholder="Insira o nome da empresa"
          required>
        </b-form-input>
      </b-form-group>
      <b-button @click="setBusiness(businessName)" class="b-button reverse-default-color gray my-3">Próximo</b-button>
    </b-form>
</div>
</template>

<script>
  export default {
    data() {
      return {
        businessName: ''
      }
    },

    props: {
      peopleName: {
        type: String,
        default: "tudo bem?"
      }
    },

    methods: {
      setBusiness(businessName) {
        this.$emit("setBusiness", { businessName })
      }
    }
  }
</script>
