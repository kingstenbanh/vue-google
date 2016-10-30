<template lang="html">
  <ul class="kb-nav">
    <li class="kb-nav__item" v-for="link in links">
      <a class="kb-nav__link" :href="link.src">{{ link.text }}</a>
    </li>
    <slot></slot>
  </ul>
</template>

<script>
export default {
  name: 'nav-link',
  components: {

  },
  props: ['links'],
};
</script>

<style lang="scss" scoped>
  a {
    text-decoration: none;
  }

  .kb-nav {
    margin: 0;
    padding-left: 0;

    &__item {
      display: inline;

      &:last-child {
        margin-right: 16px;
      }
    }

    &__link {
      color: #222;
      font-size: 13px;
      line-height: 40px;
      padding-left: 28px;
      margin: 0;

      &:hover {
        text-decoration: underline;
      }
    }
  }
</style>
