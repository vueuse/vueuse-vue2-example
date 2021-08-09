<template>
  <div id="app">
    <img src="./logo.svg" />
    <h1>Hello <a href='https://github.com/vuejs/vue' target='__blank'>Vue 2</a> and <a href='https://github.com/vueuse/vueuse' target='__blank'>VueUse</a>!</h1>

    <h3>Mouse: {{x}} x {{y}}</h3>
    <h3>
      Counter: {{count}}
      <a @click='inc()' style='margin-right:10px'>+</a>
      <a @click='dec()'>-</a>
    </h3>

    <br/><br/>
    <p><a href='https://github.com/vueuse/vueuse-vue2-example' target='__blank'>Source</a></p>
    <p><a href='https://vueuse-vue3-example.netlify.app/' target='__blank'>Vue 3 Demo</a></p>
    <p><a href='https://vueuse-vite-starter.netlify.app/' target='__blank'>Vite Starter</a></p>
  </div>
</template>

<script>
import { useMouse, useCounter } from '@vueuse/core'

export default {
  setup() {
    const { x, y } = useMouse()
    const { count, inc, dec } = useCounter()

    return {
      x, 
      y,
      count,
      inc,
      dec,
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Noto+Serif&display=swap');

html, body, h1, h2, h3, p {
  font-family: 'Noto Serif', serif;
  user-select: none;
}

#app {
  text-align: center;
  color: rgba(0,0,0,0.4);
}
img {
  width: 500px;
}
a {
  color: #41b883;
  text-decoration: none;
  cursor: pointer;
}
</style>
