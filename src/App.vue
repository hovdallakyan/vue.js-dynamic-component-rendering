<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <dynamic-link
      :type="viewState"
      :data="func"
    />
    <button @click="changeViewState('videos', {fc: () => 1+4, obj: 'hello string'})">video</button>
    <button @click="changeViewState('graph', 'hello graph!!!')">graph</button>
    <button @click="changeViewState('photo', () => 10+10)">photo</button>
  </div>

</template>

<script>
  import DynamicLink from './components/dynamic-link';

  export default {
    name: 'app',
    components: {
      DynamicLink
    },
    data() {
          return {
              viewState: 'graph',
              func: null
          }
    },
    methods: {
      changeViewState: function(item, fc) {
        this.viewState = item;
        this.func = fc;
      }
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
