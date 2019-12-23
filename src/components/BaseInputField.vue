<template>
  <input
    class="input-field"
    :type="type"
    :placeholder="placeholder"
    :value="value"
    @change="$emit('change', $event.target.value)"
  >
</template>

<script>
export default {
  name: 'BaseInputField',
  props: ['type', 'placeholder', 'value'],
  model: {
    prop: 'value',
    event: 'change',
  },
};
</script>

<style lang="scss" scoped>
.input-field {
  padding: 10px;
  background: #0004;
  border: 1px solid #0004;
  outline: none;
  margin: 0;
  color: #fff;
  text-align: center;
  transition: ease .2s;
  width: 100%;

  &::placeholder {
    color: #fffa;
  }

  &::-webkit-inner-spin-button {
    -webkit-appearance: none;
  }

  &:focus {
    border-color: #000;
  }
}
</style>
