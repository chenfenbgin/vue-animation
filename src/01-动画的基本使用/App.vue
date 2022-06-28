<template>
  <div id="app">
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
    </div>
    <!-- <h2 v-if="isShow">hello world</h2> -->

    <!-- 单元素或者组件实现过渡动画，可以使用transition内置组件来实现 -->
    <!-- 这里只要把样式name=chen,这么写就行，然后到style里面编写 -->
    <transition name="chen">
      <h2 class="title" v-if="isShow">hello world</h2>
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
  method: {},
};
</script>

<style scoped>
.title {
  display: inline-block;
}
/* 过渡动画的使用 */
/* .chen-enter-from,
.chen-leave-to { */
/* 从透明度0开始进入 */
/* opacity: 0;
} */

/* 这一部分其实是可以不写的，浏览器默认会给h2设置一个默认值1 */
/* .chen-leave-from,
.chen-enter-to {
  opacity: 1;
} */

/* .chen-enter-active,
.chen-leave-active { */
/* transition是设置具体过渡的属性, 后面跟的是对哪个属性进行过渡， ease:动画进入的方式 */
/* transition: opacity 2s ease;
} */

/* animation: 动画的名字 时间 动画执行的速率*/
.chen-enter-active {
  animation: bounce 1s ease;
}

/* reverse：动画反转 */
.chen-leave-active {
  animation: bounce 1s ease reverse;
}

/* 定义每一帧，每一帧要达到什么样的效果 */
/* @keyframes: 帧动画 + 名字 */
@keyframes bounce {
  0% {
    /* 定义缩放程度 */
    transform: scale(0);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
</style>
