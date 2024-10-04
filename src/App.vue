<script setup></script>

<template>
  <div class="bg-white rounded-[20px]">
    <header
      class="flex justify-between items-center py-[43px] border-b-gray-200 border-b px-[45px]"
    >
      <img src="./assets/sneakers.svg" alt="" />
      <nav class="flex gap-[32px] item-center">
        <RouterLink class="flex gap-[10px]" to="/">
          <img src="./assets/basket.svg" alt="" />
          <span>1205 руб.</span>
        </RouterLink>
        <RouterLink class="flex gap-[10px]" to="/favorite">
          <img src="./assets/heart.svg" alt="" />
          <span>Закладки</span>
        </RouterLink>
      </nav>
    </header>

    <div class="p-[60px]"><RouterView /></div>
  </div>
</template>

<style>
body {
  background: #e7f6ff;
  padding: 85px;
}
</style>
