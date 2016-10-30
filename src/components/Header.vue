<template lang="html">
  <header class="kb-header">
    <slot></slot>
  </header>
</template>

<script>
export default {
  name: 'header',
  components: {

  },
};
</script>

<style lang="scss" scoped>
  .kb-header {
    display: flex;
    align-items: center;
    justify-content: flex-end;;
  }
</style>
