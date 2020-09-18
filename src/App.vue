<template>
  <div id="app">
    <HelloWorld />
    <button @click="sendMessage">Send a message</button>
  </div>
</template>

<script>
import eventHub from './eventHub';
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  methods: {
    sendMessage() {
      eventHub.$emit('new-message', 'I`ve got a message!');
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
