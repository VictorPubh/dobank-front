<template>
  <div class="component white">
    <h1 class="form-title white medium py2 pb0"> Confirme seu e-mail! </h1>
    <b-form>
      <b-form-group
        id="input-group"
        :label="`Enviamos um e-mail para ${email}`"
        label-for="input-email">
        <b-form-input
          id="input"
          v-model="code"
          v-mask="['###-###']"
          type="text"
          placeholder="Insira o código"
          required>
        </b-form-input>
      </b-form-group>
      <h4 class="t1 my-3"> Reenviar código </h4>
      <b-button @click="setCode(code)" class="b-button reverse-default-color my-3">Confirmar</b-button>
      <b-button @click="changeEmail" class="b-button medium white-outline my-3 mt-0">Alterar E-mail</b-button>
    </b-form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        code: ''
      }
    },

    props: {
      email: {
        type: String
      }
    },

    methods: {
      setCode(code) {
        this.$emit("setCode", { code })
      },
      changeEmail() {
        this.$emit("changeEmail")
      }
    }
  }
</script>
