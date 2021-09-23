<template>
  <main id="app">
    <section class="roles">
      <ClassPage
          v-for="role in roles"
          :key="role.title"
          :role="role"/>
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
      roles: [
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
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'monsteratt', sans-serif;
}

main {
  width: 100vw;
  min-height: 100vh;
  overflow: hidden;

  background-color: #EEE;
  display: flex;
  justify-content: center;
  align-items: center;
}

.roles {
  display: flex;
  max-width: 1280px;
  padding: 25px;
  margin: 0 auto;
}
</style>
