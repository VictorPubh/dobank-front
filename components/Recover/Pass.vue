<template>

  <div class="component white">
    <b-form @submit="onSubmit" v-if="show">
      <b-form-group
       class="mt-3"
       label="Insira uma senha nova"
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
      <b-button type="submit" class="b-button reverse-default-color my-3">Alterar senha</b-button>
    </b-form-group>
    </b-form>

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
  .forget {
    font-size: 0.95rem;
    text-decoration: underline;
    text-align: center;
    color: rgba(255, 255, 255, 0.85);
  }
.form-group > .d-block {
  text-align: center;
}
</style>
