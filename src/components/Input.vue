<template lang="html">
  <div class="kb-input">
    <input type="text" name="name" class="kb-input__field" :style="styles">
    <i v-if="icon" class="material-icons kb-input__icon">{{ icon }}</i>
  </div>
</template>

<script>
export default {
  name: 'input',
  components: {

  },
  props: ['icon'],
  computed: {
    styles() {
      return {
        marginLeft: this.icon ? '42px' : 0,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
  input {
    &:active,
    &:focus {
      outline: none;
    }
  }

  .kb-input {
    position: relative;

    &__field {
      border: 1px solid #d1d1d1;
      border-radius: 1px;
      font-size: 14px;
      line-height: 26px;
      height: 26px;
      min-width: 200px;
      padding: 8px 42px 8px 8px;

      &:hover {
        border-color: #a0a0a0 #b9b9b9 #b9b9b9 #b9b9b9;
      }

      &:active,
      &:focus {
        border-color: #4d90fe;
      }
    }

    &__icon {
      color: #777;
      padding: 9px;
      position: relative;
      top: -1px;
      right: 47px;
      vertical-align: middle;
    }
  }
</style>
