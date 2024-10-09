<script setup>
import { ref } from "vue";


const isOpen = ref(false);
const totalSum = ref(0)

const changeIsOpen = () => {
  isOpen.value = false;
};
const addToCart = (e) => {
  totalSum.value += e 
}
const deleteFromCart = (e) => {
  totalSum.value -= e 
}

</script>

<template>
  <div class="bg-white rounded-[20px]">
    <header
      class="flex justify-between items-center py-[43px] border-b-gray-200 border-b px-[45px]"
    >
      <img src="./assets/sneakers.svg" alt="" />
      <nav class="flex gap-[32px] item-center">
        <div class="flex gap-[10px]" @click="isOpen = true">
          <img class="cursor-pointer" src="./assets/basket.svg" alt="" />
          <span class="cursor-pointer" :total="total">{{totalSum}} c.</span>
        </div>
        <RouterLink class="flex gap-[10px]" to="/favorite">
          <img src="./assets/heart.svg" alt="" />
          <span>Закладки</span>
        </RouterLink>
      </nav>
    </header>

    <div class="p-[60px]"><RouterView :isOpen="isOpen" @bob="changeIsOpen" @total="addToCart" @topaz="deleteFromCart"/></div>
  </div>
</template>

<style>
body {
  background: #e7f6ff;
  padding: 85px;
}
</style>
