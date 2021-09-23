<template>
  <div class="role">
    <div :class="'role--inner ' + role.color">
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
}
.role--inner {
  position: relative;
  padding: 25px;
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  perspective: 1000px;
}
.role--inner.green {
  background-image: linear-gradient(to bottom right, #24D484, #116432);
}
.role--inner.purple {
  background-image: linear-gradient(to bottom left, #24D484, #2474C4 70%);
}
.role--inner.pink {
  background-image: linear-gradient(to bottom right, #F444A4, #1168D4);
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
}

</style>
