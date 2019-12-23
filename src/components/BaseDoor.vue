<template>
  <div class="door-area">
    <div
      class="door-frame"
      :class="{'door-frame--selected': isSelected && !isOpened}"
    >
      <the-gift-box v-if="hasGiftBox"/>
    </div>
    <div
      class="door"
      :class="{ 'door--opened': isOpened }"
      @click="isSelected = !isSelected"
    >
      <div
        v-if="!isOpened"
        class="door__number"
        :class="{'door__number--selected': isSelected}"
      >
        {{ doorNumber }}
      </div>
      <div
        v-if="!isOpened"
        @click.stop="isOpened = true"
        class="door__knob"
        :class="{'door__knob--selected': isSelected}"
      ></div>
    </div>
  </div>
</template>

<script>
import TheGiftBox from './TheGiftBox.vue';

export default {
  name: 'BaseDoor',
  components: {
    TheGiftBox,
  },
  data: () => ({
    isSelected: false,
    isOpened: false,
  }),
  props: {
    doorNumber: {
      type: Number,
    },
    hasGiftBox: {
      type: Boolean,
    },
  },
};
</script>

<style lang="scss" scoped>
$door-border: 5px solid brown;

.door-area {
  display: flex;
  justify-content: center;
  position: relative;
  height: 310px;
  width: 200px;
  margin-bottom: 40px;
  border-bottom: 10px solid #AAA;
}

.door-frame {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  position: absolute;
  height: 300px;
  width: 180px;
  border-top: $door-border;
  border-left: $door-border;
  border-right: $door-border;

  &--selected {
    border-top-color: yellow;
    border-left-color: yellow;
    border-right-color: yellow;
  }
}

.door {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  position: absolute;
  top: 5px;
  height: 295px;
  width: 170px;
  background: chocolate;
  cursor: pointer;

  &--opened {
    background: #0004;
    cursor: initial;
  }

  &__number {
    font-size: 3rem;

    &--selected {
      color: yellow;
    }
  }

  &__knob {
    height: 20px;
    width: 20px;
    border-radius: 10px;
    background: brown;
    align-self: flex-start;
    margin-top: 60px;

    &--selected {
      background: yellow;
    }
  }
}
</style>
