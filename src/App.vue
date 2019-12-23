<template>
  <div id="app">
    <base-card class="header-card">
      <h1>Monty Hall Problem</h1>
    </base-card>
    <base-card class="form-card">
      <div>
        <label for="doors-amount">How many doors do you want?</label>
        <input type="number" id="doors-amount" value="3" max="100">
      </div>
      <div>
        <label for="selected-door">Which door has the gift?</label>
        <input type="number" id="selected-door" value="0" max="100">
      </div>
      <button>Start</button>
    </base-card>
  </div>
</template>

<script>
import BaseCard from './components/BaseCard.vue';

export default {
  name: 'app',
  components: {
    BaseCard,
  },
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
  margin: 20px 0 60px 0;
}

.form-card {
  display: flex;
  flex-direction: column;
  align-items: center;

  &, input, button {
    margin-bottom: 10px;
    font-size: 2rem;
  }
}
</style>
