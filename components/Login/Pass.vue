<template>

  <div class="component white">
    <h1 class="form-title"> Seja bem vindo ao <b>DoBank</b>! </h1>
    <b-form @submit="onSubmit" v-if="show">
      <b-form-group id="input-group"
       class="mt-3"
       label="Qual é a sua senha de acesso?"
       label-for="input-email">
       <b-input-group id="input-group">
        <b-form-input id="input"
          v-model="form.pass"
          :type="type"
          placeholder="Insira a sua senha"
          required>
        </b-form-input>

        <template #append>
            <b-input-group-text class="button-invisible" @click="showPassword">
              <span :class="`mdi mdi-${eye_icon} h5`"></span>
            </b-input-group-text>
          </template>

        </b-input-group>
        </b-form-group>
      <b-button type="submit" class="b-button reverse-default-color my-3">Próximo</b-button>
    </b-form>

    <h4 class="t1 my-3"> Esqueceu a senha? </h4>

  </div>

</template>

<script>

  export default {
    data() {
      return {
        form: {
          pass: ''
        },
        show: true,
        type: 'password',
        eye_icon: 'eye'
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      showPassword() {
        if (this.type === 'password') {
          this.type = 'text'
          this.eye_icon = 'eye-off'
        } else {
          this.type = 'password'
          this.eye_icon = 'eye'
        }
      }
    }
  }

</script>

<style>
  .button-invisible {
    background-color: transparent;
    border: 0;
    position: absolute;
    z-index: 999;
    right: 0.75rem;
    top: 0.35rem;
    color: rgba(255, 255, 255, 0.75);
  }
</style>
