<template>
  <div id="app">
    <base-card class="header-card">
      <h1>Monty Hall Problem</h1>
    </base-card>
    <base-card class="form-card" v-if="!isStarted">
      <div>
        <base-input-field
          v-model.number="numberOfDoors"
          type="number"
          placeholder="How many doors do you want?"
        />
      </div>
      <div>
        <base-input-field
          v-model.number="doorWithGiftBox"
          type="number"
          placeholder="Which door has the gift?"
        />
      </div>
      <base-button
        @click="isStarted = true"
        @keyup="isStarted = true"
      >
        Start
      </base-button>
    </base-card>
    <div class="doors" v-if="isStarted">
      <div v-for="door in numberOfDoors" :key="door">
        <base-door :doorNumber="door" :hasGiftBox="door === doorWithGiftBox" />
      </div>
    </div>
  </div>
</template>

<script>
import BaseCard from './components/BaseCard.vue';
import BaseDoor from './components/BaseDoor.vue';
import BaseInputField from './components/BaseInputField.vue';
import BaseButton from './components/BaseButton.vue';

export default {
  name: 'app',
  components: {
    BaseCard,
    BaseDoor,
    BaseInputField,
    BaseButton,
  },
  data: () => ({
    isStarted: false,
    numberOfDoors: null,
    doorWithGiftBox: null,
  }),
};
</script>

<style lang="scss">
* {
  font-family: Montserrat, sans-serif;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  color: #fff;
  background: linear-gradient(to right, #67b26f, #4ca2cd);
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.header-card {
  text-align: center;
  margin: 20px 0 60px 0;
  min-width: 560px;
  width: 50%;
}

.form-card {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-width: 560px;
  width: 50%;

  &, div, input, button {
    margin-bottom: 10px;
    font-size: 2rem;
  }
}

.doors {
  align-self: stretch;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>
