<template>
  <div id="app">
    <button @click="isShow = !isShow">显示/隐藏</button>

    <transition name="chen" mode="out-in" appear>
      <h2 v-if="isShow">Hello World</h2>
    </transition>
  </div>
</template>

<script type="text/javascript">
export default {
  name: "app",
  data() {
    return {
      isShow: true,
    };
  },
  components: {},
};
</script>

<style scoped>
.chen-enter-active,
.chen-leave-active {
  animation: bounceInUp 1s ease-in;
}
</style>
