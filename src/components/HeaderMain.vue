<template>
  <header>
    <md-toolbar>
      <md-button class="md-icon-button" @click="toggleMenu"> <md-icon>menu</md-icon> </md-button>
        <span class="md-title">myBücher<span class="subtitle md-xsmall-hide"> - Seus livros em um só lugar</span></span>
      </md-toolbar>
      <md-drawer :md-active.sync="showNavigation">
        <md-toolbar class="md-transparent" md-elevation="0">
          <span class="md-title">O que você quer fazer?</span>
        </md-toolbar>

        <md-list>
          <router-link to="/" @click.native="toggleMenu">
            <md-list-item>
              <md-icon>home</md-icon>
              <span class="md-list-item-text">Lista de livros</span>
            </md-list-item>
          </router-link>

          <router-link to="/book" @click.native="toggleMenu">
            <md-list-item>
              <md-icon>add</md-icon>
              <span class="md-list-item-text">Cadastrar livro</span>
            </md-list-item>
          </router-link>

        </md-list>
      </md-drawer>
  </header>
</template>

<script>
export default {
  name: 'HeaderMain',

  data () {
    return {
      showNavigation: false
    }
  },

  methods: {
    toggleMenu: function () {
      this.showNavigation = !this.showNavigation
    }
  }
}
</script>
