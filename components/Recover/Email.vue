<template>
  <div class="component white">
    <b-form @submit="onSubmit" v-if="show">
      <b-form-group
        id="input-group"
        label="Qual é o seu e-mail?"
        description="Vamos te enviar um e-mail com as instruções."
        label-for="input-email">
        <b-form-input
          id="input"
          v-model="form.email"
          type="email"
          placeholder="Insira seu e-mail"
          required>
        </b-form-input>
      </b-form-group>
      <b-button type="submit" class="b-button reverse-default-color my-3">Próximo</b-button>
    </b-form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          email: ''
        },
        show: true
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      }
    }
  }
</script>
