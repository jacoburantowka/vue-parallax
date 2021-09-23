<template>
  <div class="role">
    <div :class="'role--inner ' + role.title.toLowerCase()">
      <div class="role--text-wrap">
        <h2 class="bg-text">{{ role.bgtext }}</h2>
      </div>
      <div class="role--image-wrap">
        <img :src="role.src"
             :alt="imgAlt(role.title)"
             class="image">
      </div>
      <div class="role--detail">
        <h2>{{ role.title }}</h2>
        <p><span>{{ role.description }}</span></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ClassPage",
  props: ['role'],
  methods: {
    imgAlt (name) {
      return `${name} class emblem.`
    }
  }
}
</script>

<style scoped>
.role {
  flex: 1 1 33.333%;
  width: 100%;
  padding: 25px;
  min-width: 250px;
}
.role--inner {
  position: relative;
  padding: 25px;
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  perspective: 1000px;
}
.role--inner.barbarian {
  background-image: linear-gradient(to bottom right,#c25c63, #d57589);
}
.role--inner.bard {
  background-image: linear-gradient(to bottom right, #e88daf, #e1a785);
}
.role--inner.cleric {
  background-image: linear-gradient(to bottom right, #dac15b, #b3ae64);
}
.role--inner.druid {
  background-image: linear-gradient(to bottom right, #8b9a6c, #929780);
}
.role--inner.fighter {
  background-image: linear-gradient(to bottom right, #989494, #7f8897);
}
.role--inner.monk {
  background-image: linear-gradient(to bottom right, #667b9a, #a9927c);
}
.role--inner.paladin {
  background-image: linear-gradient(to bottom right, #eca85d, #aba476);
}
.role--inner.ranger {
  background-image: linear-gradient(to bottom right, #69a08f, #848f6c);
}
.role--inner.rogue {
  background-image: linear-gradient(to bottom right, #9f7e49, #c3825a);
}
.role--inner.sorcerer {
  background-image: linear-gradient(to bottom right, #e7866b, #bf838c);
}
.role--inner.warlock {
  background-image: linear-gradient(to bottom right, #977fad, #637d98);
}
.role--inner.wizard {
  background-image: linear-gradient(to bottom right, #2e7b83, #fff);
}
.role--text-wrap {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
  overflow: hidden;
  perspective: 1000px;
}

.role--text-wrap h2 {
  color: #313131;
  font-size: 128px;
  font-weight: 900;
  opacity: 0.2;
  transform-origin: center;
}
.role--image-wrap {
  position: relative;
  z-index: 1;
  transform-origin: center;
}

.role--image-wrap .image {
  width: 100%;
  filter: drop-shadow(0px 0px 12px rgba(0, 0, 0, 0.25));
}
.role--detail {
  background-color: #FFF;
  padding: 25px;
  margin: 0px -25px -25px;
  height: 300px;
  display: flex;
  flex-direction: column;
}
.role--detail h2 {
  font-size: 24px;
  font-weight: 700;
  color: #676767;
  margin-bottom: 15px;
}
.role--detail p {
  font-size: 14px;
  line-height: 1.5;
  font-weight: 300;
  color: #676767;
  justify-content: center;
}

</style>
