<template>
  <div id="app">
    <drop-area width="800px" height="500px" />
    <div class="icons">
      <draggable-icon v-for="(func,index) in functions" :func="func" :key="index" />
    </div>
  </div>
</template>

<script>
import DropArea from './components/DropArea'
import DraggableIcon from './components/DraggableIcon'

const add = (a, b) => a + b
const subtract = (a, b) => a - b
const foo = (a, b, c) => a + b - c
const doSomethingComplicate = (a) => a + a - a + a - a

const sampleFuncions = [add, subtract, foo, doSomethingComplicate]

export default {
  name: 'App',
  components: {
    DropArea,
    DraggableIcon
  },
  data () {
    return {
      functions: sampleFuncions
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

p, span {
  margin: 0;
  addping: 0;
}
</style>
