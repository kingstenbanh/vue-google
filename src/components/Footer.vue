<template lang="html">
  <footer class="kb-footer">
    <slot></slot>
  </footer>
</template>

<script>
export default {
  name: 'footer',
  components: {

  },
};
</script>

<style lang="scss" scoped>
  .kb-footer {
    background-color: #f2f2f2;
    border-top: 1px solid #e4e4e4;
    bottom: 0;
    display: flex;
    justify-content: space-between;
    left: 0;
    position: absolute;
    right: 0;
    width: 100%;
  }
</style>
