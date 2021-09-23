<template>
  <main id="app" @mousemove="mouseMove">
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
          title: 'Barbarian',
          color: 'flame',
          bgtext: 'BRBRN',
          src: require('./assets/Class Icon - Barbarian.svg'),
          description: 'For some, their rage springs from a communion with fierce animal spirits. Others draw from a roiling reservoir of anger at a world full of pain. For every barbarian, rage is a power that fuels not just a battle frenzy but also uncanny reflexes, resilience, and feats of strength.'
        },
        {
          title: 'Bard',
          color: 'pink',
          bgtext: 'BRD',
          src: require('./assets/Class Icon - Bard.svg'),
          description: 'Whether scholar, skald, or scoundrel, a bard weaves magic through words and music to inspire allies, demoralize foes, manipulate minds, create illusions, and even heal wounds. The bard is a master of song, speech, and the magic they contain.'
        },
        {
          title: 'Cleric',
          color: 'purple',
          bgtext: 'CLRC',
          src: require('./assets/Class Icon - Cleric.svg'),
          description: 'Clerics are intermediaries between the mortal world and the distant planes of the gods. As varied as the gods they serve, clerics strive to embody the handiwork of their deities. No ordinary priest, a cleric is imbued with divine magic.'
        },
        {
          title: 'Druid',
          color: 'green',
          bgtext: 'DRD',
          src: require('./assets/Class Icon - Druid.svg'),
          description: 'Whether calling on the elemental forces of nature or emulating the creatures of the animal world, druids are an embodiment of nature\'s resilience, cunning, and fury. They claim no mastery over nature, but see themselves as extensions of nature\'s indomitable will.'
        },
        {
          title: 'Fighter',
          color: 'pink',
          bgtext: 'FGHTR',
          src: require('./assets/Class Icon - Fighter.svg'),
          description: 'Fighters share an unparalleled mastery with weapons and armor, and a thorough knowledge of the skills of combat. They are well acquainted with death, both meting it out and staring it defiantly in the face.'
        },
        {
          title: 'Monk',
          color: 'purple',
          bgtext: 'MNK',
          src: require('./assets/Class Icon - Monk.svg'),
          description: 'Monks are united in their ability to magically harness the energy that flows in their bodies. Whether channeled as a striking display of combat prowess or a subtler focus of defensive ability and speed, this energy infuses all that a monk does.'
        },
        {
          title: 'Paladin',
          color: 'green',
          bgtext: 'PLDN',
          src: require('./assets/Class Icon - Paladin.svg'),
          description: 'Whether sworn before a god\'s altar and the witness of a priest, in a sacred glade before nature spirits and fey beings, or in a moment of desperation and grief with the dead as the only witness, a paladin\'s oath is a powerful bond.'
        },
        {
          title: 'Ranger',
          color: 'pink',
          bgtext: 'RNGR',
          src: require('./assets/Class Icon - Ranger.svg'),
          description: 'Far from the bustle of cities and towns, past the hedges that shelter the most distant farms from the terrors of the wild, amid the dense-packed trees of trackless forests and across wide and empty plains, rangers keep their unending watch.'
        },
        {
          title: 'Rogue',
          color: 'purple',
          bgtext: 'RG',
          src: require('./assets/Class Icon - Rogue.svg'),
          description: 'Rogues rely on skill, stealth, and their foes\' vulnerabilities to get the upper hand in any situation. They have a knack for finding the solution to just about any problem, demonstrating a resourcefulness and versatility that is the cornerstone of any successful adventuring party.'
        },
        {
          title: 'Sorcerer',
          color: 'green',
          bgtext: 'SRCRR',
          src: require('./assets/Class Icon - Sorcerer.svg'),
          description: 'Sorcerers carry a magical birthright conferred upon them by an exotic bloodline, some otherworldly influence, or exposure to unknown cosmic forces. No one chooses sorcery; the power chooses the sorcerer.'
        },
        {
          title: 'Warlock',
          color: 'pink',
          bgtext: 'WRLCK',
          src: require('./assets/Class Icon - Warlock.svg'),
          description: 'Warlocks are seekers of the knowledge that lies hidden in the fabric of the multiverse. Through pacts made with mysterious beings of supernatural power, warlocks unlock magical effects both subtle and spectacular.'
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
    mouseMove (e) {
      let mouseX = e.clientX
      let mouseY = e.clientY

      let roles = document.querySelectorAll('.roles .role')

      for (let i = 0; i < roles.length; i++) {
        let role = roles[i];
        let roleImg = role.querySelector('.role--image-wrap');
        let img_x = mouseX - this.coords(roleImg).x;
        let img_y = mouseY - this.coords(roleImg).y;
        roleImg.style.transform = `translateY(-${img_y/40}px) translateX(-${img_x/40}px) translateZ(100px)`;
        let bgText = role.querySelector('.bg-text');
        let bg_x = mouseX - this.coords(bgText).x;
        bgText.style.transform = `translateX(${bg_x/25}px)`;
      }
    },
    coords (el) {
      let coords = el.getBoundingClientRect();
      return {
        x: coords.left / 2,
        y: coords.top / 2
      }
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
  flex-wrap: wrap;
  max-width: 1280px;
  padding: 25px;
  margin: 0 auto;
}
</style>
