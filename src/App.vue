<script setup>
import { ref } from "vue";

const isOpen = ref(false);

const changeIsOpen = () => {
  isOpen.value = false;
};
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
          <span class="cursor-pointer">1205 руб.</span>
        </div>
        <RouterLink class="flex gap-[10px]" to="/favorite">
          <img src="./assets/heart.svg" alt="" />
          <span>Закладки</span>
        </RouterLink>
      </nav>
    </header>

    <div class="p-[60px]"><RouterView :isOpen="isOpen" @bob="changeIsOpen" /></div>
  </div>
</template>

<style>
body {
  background: #e7f6ff;
  padding: 85px;
}
</style>
