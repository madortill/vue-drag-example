<template>
  <div class="drag-el" draggable="true" @dragstart="startDrag"></div>
    <div class="drop-zone" @drop="onDrop" @dragover.prevent @dragenter.prevent></div>
</template>

<script>
  export default {
  methods: {
    startDrag(evt) {
      evt.dataTransfer.dropEffect = 'move';
      evt.dataTransfer.effectAllowed = 'move';
      event.dataTransfer.setData("text/plain", "This text may be dragged");
    },
    onDrop() {
      alert('success');
    },
  },
}
</script>


<style scoped>
  .drop-zone {
    width: 16rem;
    height: 16rem;
    border: dashed black 2px;
  }

  .drag-el {
    border-radius: 50%;
    background-color: pink;
    width: 5rem;
    height: 5rem;
  }
</style>
