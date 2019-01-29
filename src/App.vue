<template>
  <div id="app">
    <button v-on:click="show = !show">Toggle Button</button>
    <transition name="hello">
      <p v-if="show">Hello</p>
    </transition>
    <button v-on:click="slide = !slide">Toggle Slide</button>
    <transition name="slide">
      <p v-if="slide">Hello</p>
    </transition>
    <button @click="customClass = !customClass">Toggle Custom Class</button>
    <transition
      name="custom-classes-transition"
      enter-active-class="animated tada"
      leave-active-class="animated bounceOutRight"
    >
      <p v-if="customClass">hello</p>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: true,
      slide: true,
      customClass: true
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.hello-enter,
.hello-leave-to {
  opacity: 0;
}

.hello-enter-active,
.hello-leave-active {
  transition: opacity 1.5s;
}

.slide-enter,
.slide-leave-to {
  width: 30%;
  opacity: 0;
  transform: translateX(30px);
}

.slide-leave-to {
  transform: translateX(-30px);
}

.slide-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-enter-active {
  transition: all 0.8s ease;
}
</style>
