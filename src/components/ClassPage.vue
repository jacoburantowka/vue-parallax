<template>
  <div class="role">
    <div class="role--inner">
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
        <p><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor, ducimus eius est eum ex hic in laborum minus nam nulla porro temporibus vel. Consequuntur dolorum ex impedit quam quia, temporibus?</span></p>
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
</style>