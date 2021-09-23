<template>
  <div class="role">
    <div :class="'role--inner ' + role.color">
      <div class="role--text-wrap">
        <h2 class="bg--text">{{ role.bgtext }}</h2>
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
}

.role--inner.green {
  background-image: linear-gradient(to top right, rgba(17, 100, 50, 0.47), #24D484);

}

.role--inner.pink {
  background-image: linear-gradient(to bottom left, #F444A4, #24D484 70%);

}

.role--inner.purple {
  background-image: linear-gradient(to bottom left, #69b1f1, #F444A4 70%);

}

.role--text-wrap {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 0;
  overflow: hidden;
}

.role--text-wrap h2 {
  color: #313131;
  font-size: 8em;
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
  filter: drop-shadow(0px 0px 12px rgba(0, 0, 0, 0.1));
}


.role--detail {
  background-color: #fff;
  padding: 25px;
  margin: 0 -25px -25px;
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
  color: #676;
}

</style>
