<template>
  <div class="card">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'BaseCard',
};
</script>

<style lang="scss" scoped>
.card {
  border: 1px solid #000;
  background: #0004;
  padding: 20px;
}
</style>
