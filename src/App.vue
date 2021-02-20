<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from 'vue';
import HelloWorld from './components/HelloWorld.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const simpleRef1 = ref<string>('');
    const simpleRef2 = ref<string>('');
    const consumeStrings = (s1: string, s2: string) => { console.log(s1 + s2) };

    watch([simpleRef1, simpleRef2], ([newString1, newString2]) => {
      consumeStrings(newString1, newString2)
    })
  }
});
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
