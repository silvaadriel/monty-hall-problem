<template>
  <button
    @click="$emit('click')"
    class="base-button"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
};
</script>

<style lang="scss" scoped>
.base-button {
  background: #0004;
  color: #fff;
  outline: none;
  padding: 10px;
  border: 1px solid #000;
  cursor: pointer;
  transition: ease .2s;

  &:hover {
    background: #0008;
  }
}
</style>
