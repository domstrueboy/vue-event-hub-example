<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import eventHub from '../eventHub';

export default {
  name: 'HelloWorld',
  data: () => ({
    msg: 'Hello world!',
  }),
  created: function () {
    eventHub.$on('new-message', this.newMessageHandler);
  },
  methods: {
    newMessageHandler(payload) {
      this.msg = payload;
    }
  },
  beforeDestroy: function () {
    eventHub.$off('new-message', this.newMessageHandler);
  },
}
</script>
