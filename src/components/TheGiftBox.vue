<template>
  <div class="gift-box">
    <div class="gift-box__cover"></div>
    <div class="gift-box__body"></div>
  </div>
</template>

<script>
export default {
  name: 'TheGiftBox',
};
</script>

<style lang="scss" scoped>
.gift-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;

  &::before {
    content: "";
    position: absolute;
    height: 85px;
    width: 15px;
    background: red;
  }

  &::after {
    content: "";
    position: absolute;
    height: 15px;
    width: 90px;
    top: 40px;
    background: red;
  }

  &__cover {
    height: 25px;
    width: 100px;
    background: #7aa944;
  }

  &__body {
    height: 60px;
    width: 90px;
    background: #5c7e32;
  }
}
</style>
