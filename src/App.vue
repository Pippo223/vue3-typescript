<template>
  <div id="app">
    <h1>{{ name }} - {{ age }}</h1>
    <button @click="changeName('Zelda')"> Change Name</button>
    <button @click="changeAge(34)"> Change Age</button>
  </div>
</template>

<script lang="ts">
    import { defineComponent, reactive, toRefs } from 'vue';

    export default defineComponent({
      name: 'App',
      components: {},
      setup() {
        const state = reactive({
          name: 'Link',
          age: 25 as string | number
        })
        state.name = 999  // will not work
        return { ...toRefs(state)}
      },
       
      methods: {
        changeName(name: string) {
          this.name = name
        },
        changeAge(age: string | number ) {
        this.age = age
      }
      }, 
      
    });
</script>

<style lang="scss">
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  // color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
