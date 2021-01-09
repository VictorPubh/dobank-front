<template>
  <div class="component white">
    <b-form @submit="onSubmit" v-if="show">
      <b-form-group
        id="input-group"
        label="Insira seu código"
        label-for="input-email">
        <b-form-input
          id="input"
          v-model="form.code"
          type="number"
          placeholder="Insira seu código"
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
          code: ''
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
