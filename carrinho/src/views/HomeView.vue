<!-- eslint-disable no-unused-vars -->
<script setup>
import { ref } from 'vue';
import SlidePanel from '../components/shared/SlidePanel.vue';


 const cartVisible = ref(true);

 const changeCartVisibility = () => {
  cartVisible.value = !cartVisible.value;
  console.log(cartVisible.value);
 };

</script>

<template>
  <div class="home">
    <h1> Shopping Cart</h1>
    <button class="btn success">Add to Cart</button>
    <button class="btn error ml-1">Clear Cart</button>
    <button
      class="btn error ml-1"
      @click="changeCartVisibility()">
      Open Cart</button>
      <SlidePanel
          title ="Cart"
          :visible="cartVisible"
          @update-visible="changeCartVisibility()">
      </SlidePanel>
  </div>
</template>

<style lang="scss" scoped>

.btn {
  &.primry {
    background-color: aqua;
    color: bisque;

    &:hover {
      background-color: #fff;
      color: #000;
    }
  }

  &.success {
    background-color: rgb(140, 29, 204);
    color: #000;

    &:hover {
      background-color: #8ef98e;
      color: #000;
    }
  }

    &.error {
      background-color: #ff777f;
      color: #000;

    &:hover {
      background-color: #df1cae;
      color: #000;
    }
  }

  &--outline {
    background-color: transparent;
    color: #000;

    &:hover{
    background-color: #ff777f;
    border: #ff777f;
    color:#fff
    }
  }
}

.ml-1 {
  margin-left: 3rem;
}
</style>
