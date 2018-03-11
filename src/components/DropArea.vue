<template>
  <div class='drop-area' :style="styleObject" @drop="handleDrop" @dragover="allowDrop">
    <function-item v-if="showFunctionItem" :func="functionData"></function-item>
  </div>

</template>

<script>
import FunctionItem from '@/components/FunctionItem'

export default {
  name: 'DropArea',
  props: ['width', 'height'],
  components: {
    FunctionItem
  },
  data () {
    return {
      showFunctionItem: false,
      functionData: null,
      styleObject: {
        width: this.width,
        height: this.height
      }
    }
  },
  methods: {
    handleDrop (evt) {
      evt.preventDefault()
      evt.stopPropagation()
      const funcData = event.dataTransfer.getData('text')
      this.functionData = JSON.parse(funcData)
      this.showFunctionItem = true
    },
    allowDrop (evt) {
      evt.preventDefault()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.drop-area {
  border: 2px solid #c1caca;
  display: inline-flex;
  flex-direction: column;
  justify-content: center;
  margin: 5px;
}
</style>
