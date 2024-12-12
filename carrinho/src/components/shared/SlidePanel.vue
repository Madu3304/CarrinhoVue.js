<script setup>
//criando propriedades
defineProps({
  title: {
    type: String,
    required: true
  },

  visible:{
    type: Boolean,
    required: true
  },
})

const emit = defineEmits(['update:visible'])

const closePanel = () => {
  emit('update:visible', false)
}

</script>

<template>
  <div class="panel-rap">
    <div class="panel">
      <div>
        <button class="btn error--outline"
        @click="closePanel()">
        Close
      </button>
      <h2>{{  title }}</h2>
      </div>
      <slot name="content"></slot>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.panel {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  background-color: aqua;
  color: azure;
  overflow: auto;
  padding: 1em;

  &-wrap {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: rgb(0, 0, 0, 0.5);
    z-index: 1;
  }
}
</style>

