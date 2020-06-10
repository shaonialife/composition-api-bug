<template>
  <div id="app">
    <HelloWorld
      v-if="visible"
      msg="Welcome to Your Vue.js App"
    />

    <button @click="toggle">
      toggle
    </button>
  </div>
</template>

<script>
import { reactive, toRefs } from '@vue/composition-api';
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  setup() {
    const state = reactive({
      visible: true,
    });

    const toggle = () => {
      state.visible = !state.visible;
    };

    return {
      ...toRefs(state),
      toggle,
    };
  },
};
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
