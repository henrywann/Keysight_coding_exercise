<template lang="html">
  <div draggable="true" class="draggable-icon" @dragstart="handleDrag">
    <p>{{func.name}}</p>
  </div>
</template>

<script>
export default {
  name: 'DraggableIcon',
  props: ['func'],
  methods: {
    handleDrag (evt) {
      evt.dataTransfer.effectAllowed = 'move'
      const transferData = {
        name: this.func.name,
        argLength: this.func.length
      }
      evt.dataTransfer.setData('text', JSON.stringify(transferData))
    }
  }
}
</script>

<style lang="css" scoped>
.draggable-icon {
  border: 1px solid black;
  padding: 0 10px;
  display: inline-block;
  margin: 10px;
}
</style>
