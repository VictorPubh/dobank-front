<template>
  <div class="component general white">
      <div class="progress-wrapper">
        <b-progress :value="progress.value" :max="progress.max" class="progress mx-auto m-2"></b-progress>
        <h2 class="white is-center m-2"> Passo {{ progress.value }}/{{ progress.max }} </h2>
      </div>

      <div v-if="progress.value == 0">
        <Welcome @setType="setType($event)" />
      </div>

      <div v-if="accountType == 'business' && progress.value >= 1">
        <div v-if="progress.value == 1">
          <FederalId @setFederalId="setFederalId($event)" term="CNPJ" :federalIdType="accountType" />
        </div>

        <div v-if="progress.value == 2">
          <Name @setName="setName($event)" />
        </div>

        <div v-if="progress.value == 3">
          <Business @setBusiness="setBusiness($event)" :peopleName="this.accountRegister.name" />
        </div>

        <div v-if="progress.value == 4">
          <Email @setEmail="setEmail($event)" />
        </div>

        <div v-if="progress.value == 5">
          <ConfirmEmail :email="this.accountRegister.email" @setCode="nextStep" @changeEmail="backStep" />
        </div>
      </div>

      <div v-if="accountType == 'personal' && progress.value >= 1">
          <div v-if="progress.value == 1">
            <FederalId @setFederalId="setFederalId($event)" term="CPF" :federalIdType="accountType" />
          </div>
      </div>

  </div>
</template>

<script>
import Welcome from '~/components/Register/Welcome'
import FederalId from '~/components/Register/FederalId'
import Name from '~/components/Register/Name'
import Business from '~/components/Register/Business'
import Email from '~/components/Register/Email'
import ConfirmEmail from '~/components/Register/ConfirmEmail'

export default {
  data() {
    return {
      progress: {
        value: 0,
        max: 9
      },
      accountType: 'business',
      accountRegister: {
        name: '',
        email: '',
        federalId: '',
        businessName: ''
      },
      flow: {
        business: [
          'business'
        ],
        personal: [
          'personal'
        ]
      }
    }
  },


  methods: {
    setType($event) {
      this.accountType = $event.accountType
      this.progress.value++
    },
    setName($event) {
      this.accountRegister.name = $event.name
      this.progress.value++
    },
    setFederalId($event) {
      this.accountRegister.federalId = $event.federalId
      this.progress.value++
    },
    setBusiness($event) {
      this.accountRegister.businessName = $event.businessName
      this.progress.value++
    },
    setEmail($event) {
      this.accountRegister.email = $event.email
      this.progress.value++
    },
    nextStep() {
      this.progress.value++
    },
    backStep() {
      this.progress.value--
    }
  },

  components: {
    Welcome,
    FederalId,
    Name,
    Business,
    Email,
    ConfirmEmail
  }
}
</script>

<style>
.progress-wrapper h2 {
  font-size: 0.7rem;
  color: rgba(255, 255, 255, 0.80);
  text-transform: uppercase;
}
</style>
