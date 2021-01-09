<template>
  <div>
    <h1 class="form-title white medium py2 pb0"> Seja bem vindo! </h1>
    <p class="text white is-center px4 py2">
      Para abrir sua conta digital DoBank, preciso saber qual tipo de conta você ta procurando. </p>

      <h4 class="t1 my-3"> Preciso de ajuda </h4>

    <b-button type="submit" @click="setType('business')" class="b-button medium reverse-default-color gray">Conta empresarial</b-button>
    <b-button type="submit" @click="setType('personal')" class="b-button medium white-outline my-3">Contra normal</b-button>
  </div>
</template>

<script>
export default {
  methods: {
    setType(accountType) {
      this.$emit("setType", { accountType })
    }
  }
}
</script>
