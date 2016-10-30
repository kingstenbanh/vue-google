<template>
  <div id="app" class="app">
    <vue-header>
      <nav-link :links="links.headers.right" />
      <vue-button type="icon">
        <i class="material-icons">apps</i>
      </vue-button>
      <vue-button type="primary" style="margin-right: 12px; height: 30px;">Sign In</vue-button>
    </vue-header>

    <div class="app__body">
      <img class="google-logo" src="../static/images/google.png" />
      <vue-input
        class="search-bar"
        icon="keyboard_voice"
        v-model="searchInput"
        @onEnter="search"
      />

      <div class="button-container">
        <vue-button @clickButton="search">Google Search</vue-button>
        <vue-button>I'm Feeling Lucky</vue-button>
      </div>
    </div>

    <vue-footer>
      <nav-link :links="links.footer.left"/>
      <nav-link :links="links.footer.right"/>
    </vue-footer>
  </div>
</template>

<script>
import VueButton from './components/Button';
import VueFooter from './components/Footer';
import VueHeader from './components/Header';
import VueInput from './components/Input';
import NavLink from './components/NavLink';
import Hello from './components/Hello';

export default {
  name: 'app',
  components: {
    Hello,
    VueButton,
    VueFooter,
    VueHeader,
    VueInput,
    NavLink,
  },
  data() {
    return {
      links: {
        headers: {
          right: [{
            text: 'Gmail',
            src: '//mail.google.com/mail/?tab=wm',
          }, {
            text: 'Images',
            src: '//www.google.com/imghp?hl=en&tab=wi&ei=EKoVWIvNBtC4jwOzpq6IBw&ved=0EKouCBcoAQ',
          }],
        },
        footer: {
          left: [{
            text: 'Advertising',
            src: '//www.google.com/intl/en/ads/?fg=1',
          }, {
            text: 'Business',
            src: '//www.google.com/services/?fg=1',
          }, {
            text: 'About',
            src: '//www.google.com/intl/en/about.html?fg=1',
          }],
          right: [{
            text: 'Privacy',
            src: '//www.google.com/intl/en/policies/privacy/?fg=1',
          }, {
            text: 'Terms',
            src: '//www.google.com/intl/en/policies/terms/?fg=1',
          }, {
            text: 'Settings',
            src: '//www.google.com/preferences?hl=en',
          }],
        },
      },
      searchInput: '',
    };
  },
  methods: {
    search() {
      window.location = `https://www.google.com/search?q=${this.searchInput}`; // eslint-disable-line no-undef
    },
  },
};
</script>

<style lang="scss">
  body {
    margin: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
  }

  .app {
    &__body {
      margin-top: 88px;
      padding-bottom: 36px;
    }
  }

  .google-logo {
    width: 320px;
    padding-bottom: 18px;
  }

  .search-bar {
    .kb-input__field {
      width: 450px;
    }
  }

  .button-container {
    padding-top: 18px;
  }
</style>
