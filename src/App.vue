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
          src: require('./assets/Class Icon - Ranger.svg'),
          description: 'Far from the bustle of cities and towns, past the hedges that shelter the most distant farms from the terrors of the wild, amid the dense-packed trees of trackless forests and across wide and empty plains, rangers keep their unending watch.'
        },
        {
          title: 'Bard',
          color: 'pink',
          bgtext: 'BRD',
          src: require('./assets/Class Icon - Bard.svg'),
          description: 'Whether scholar, skald, or scoundrel, a bard weaves magic through words and music to inspire allies, demoralize foes, manipulate minds, create illusions, and even heal wounds. The bard is a master of song, speech, and the magic they contain.'
        },
        {
          title: 'Wizard',
          color: 'purple',
          bgtext: 'WZRD',
          src: require('./assets/Class Icon - Wizard.svg'),
          description: 'Wizards are supreme magic-users, defined and united as a class by the spells they cast. Drawing on the subtle weave of magic that permeates the cosmos, wizards cast spells of explosive fire, arcing lightning, subtle deception, brute-force mind control, and much more.'
        }
      ]
    }
  },
  methods: {
    mouseMove () {
      
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
