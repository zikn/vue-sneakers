<template>
  <div
    class="w-[210px] h-[260px] pt-[20px] pl-[33px] pr-[44px] pb-[34px] border rounded-[40px] relative"
  >
    <img
      @click="addToLiked(sneaker)"
      v-if="isLiked"
      class="absolute top-[20px] z-10"
      src="../assets/unliked.svg"
      alt=""
    />
    <img
      @click="removeFromLiked(sneaker)"
      v-else
      class="absolute top-[20px] z-10"
      src="../assets/liked.svg"
      alt=""
    />
    <img class="relative" :src="sneaker.sneakersUrl" alt="" />
    <p class="text-[14px] text-left w-[150px]">{{ sneaker.title }}</p>

    <div class="flex justify-between mt-[14px]">
      <div class="flex flex-col">
        <span class="text-[#BDBDBD] text-[11px] uppercase">Цена:</span>
        <span class="font-bold text-[14px]"> {{ sneaker.price }}c.</span>
      </div>

      <img 
      @click="addToCart(sneaker)"
      v-if="isAdded"
      src="../assets/plus.svg"
      
       alt="" />
      <img
      @click="removeFromCart(sneaker)"
      v-else
       src="../assets/check.svg"
        alt="" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

defineProps(['sneaker']);
const emit = defineEmits();

const isLiked = ref(true);
const isAdded = ref(true);

const addToLiked = (sneaker) => {
  isLiked.value = false;
  emit('jazgul', sneaker)
};

const removeFromLiked = (sneaker) => {
    isLiked.value = true;
    emit('anjelika', sneaker)
}

const addToCart = (sneaker) => {
    isAdded.value = false;
    emit('addToCart', sneaker)
}

const removeFromCart = (sneaker) => {
    isAdded.value = true;
    emit('removeFromCart', sneaker)
}
</script>
