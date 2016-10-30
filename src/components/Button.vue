<template lang="">
  <button
    type="button"
    name="button"
    class="kb-button"
    :class="classNames"
    @click="clickButton">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'button',
  components: {

  },
  props: ['text', 'type'],
  computed: {
    classNames() {
      return {
        'kb-button--primary': this.type === 'primary',
        'kb-button--icon': this.type === 'icon',
      };
    },
  },
  methods: {
    clickButton() {
      this.$emit('clickButton');
    },
  },
};
</script>

<style lang="scss" scoped>
  button {
    &:hover,
    &:active,
    &:focus {
      outline: none;
    }
  }

  .kb-button {
    background-image: -webkit-linear-gradient(top, #f5f5f5, #f1f1f1);
    background-color: #f2f2f2;
    border: 1px solid #f2f2f2;
    border-radius: 2px;
    color: #757575;
    font-size: 13px;
    font-weight: bold;
    height: 36px;
    line-height: 27px;
    margin: 11px 4px;
    min-width: 54px;
    padding: 0 16px;
    text-align: center;

    &:hover {
      background-image: -webkit-linear-gradient(top,#f8f8f8,#f1f1f1);
      background-color: #f8f8f8;
      border-color: #c6c6c6;
      color: #222;
    }

    &--primary {
      background-image: none;
      background-color: #4285f4;
      border-color: #4285f4;
      color: #fff;

      &:hover {
        background-image: none;
        background-color: #4285f4;
        border-color: #4285f4;
        color: #fff;
      }
    }

    &--icon {
      background-image: none;
      background-color: transparent;
      border: 0;
      line-height: 12px;
      min-width: 36px;
      padding: 0;
    }
  }
</style>
