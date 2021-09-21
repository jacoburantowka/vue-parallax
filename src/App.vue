<template>
  <main id="app">
    <section class="classes">
      <ClassPage v-for="item in classes" :key="item.title"/>
    </section>
  </main>
</template>

<script>
import ClassPage from "./components/ClassPage";

export default {
  name: 'App',
  components: {
    ClassPage
  },
  data () {
    return {
      classes: [
        {
          title: 'Ranger',
          color: 'green',
          bgtext: 'RNGR',
          src: require('./assets/Class Icon - Ranger.svg')
        },
        {
          title: 'Bard',
          color: 'pink',
          bgtext: 'BRD',
          src: require('./assets/Class Icon - Bard.svg')
        },
        {
          title: 'Wizard',
          color: 'purple',
          bgtext: 'WZRD',
          src: require('./assets/Class Icon - Wizard.svg')
        }
      ]
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
