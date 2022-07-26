<template>
  <div id="app">
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
    import { defineComponent, reactive, ref, toRefs } from 'vue';
    import JobList from './components/JobsList.vue'
    import Job from './types/Jobs'

    export default defineComponent({
      name: 'App',
      components: { JobList},
      setup() {
        const jobs = ref<Job[]>([
          { id: 1, title: 'Farmer', location: 'Kadjebi', salary: 4000 },
          { id: 2, title: 'Fisherman', location: 'Dukuram', salary: 3000 },
          { id: 3, title: 'Tailor', location: 'Nsanae', salary: 4500 },
          { id: 4, title: 'Hairdresser', location: 'Ayempo', salary: 3500 },
          { id: 5, title: 'Mason', location: 'Loton', salary: 2000 }

        ])

        return { jobs }
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
