<template>
  <div id="app">
    <transition :name="transitionName">
      <vue-page-stack>
        <router-view :key="$route.fullPath" class="router-view-c" />
      </vue-page-stack>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      transitionName: ''
    }
  }
  // watch: {
  //   $route(to, from) {
  //     if (to.params['stack-key-dir'] === 'forward') {
  //       this.transitionName = 'forward'
  //     } else {
  //       this.transitionName = 'back'
  //     }
  //   }
  // }
}
</script>

<style lang="less">
#app {
  position: relative;
  min-height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: @appBg;
}
// .router-view-c {
//   position: absolute;
//   transition: opacity 0.5s, transform 0.5s;
//   width: 100%;
// }
// .forward-enter,
// .back-leave-active {
//   opacity: 0.5;
//   transform: translateX(100%);
// }
// .forward-leave-active,
// .back-enter {
//   opacity: 0.5;
//   transform: translateX(-100%);
// }
</style>
