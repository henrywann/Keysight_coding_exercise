<template lang="html">
  <div class="row">
    <div class="function-item">
      <div class="function-item-name">{{func.name}}</div>
      <drop-area width="40%" v-for="n in func.argLength" :key="n"></drop-area>
    </div>
  </div>
</template>

<script>
import DropArea from '@/components/DropArea'

export default {
  name: 'FunctionItem',
  props: ['func'],
  components: {
    DropArea
  },
  beforeCreate: function () {
    this.$options.components.DropArea = require('./DropArea').default
  }
}
</script>

<style lang="css" scoped>
.row {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.function-item {
  display: flex;
  justify-content: space-around;
  padding: 10px;
}
.function-item-name {
  padding: 5px 10px 15px;
  text-align: left;
  border: 1px solid black;
  display: inline-block;
  margin: 5px;
  max-height: 10px;
  align-self: center;
}
</style>
