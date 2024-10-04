<script setup>
import { ref } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation, Pagination, A11y } from 'swiper/modules';
import Sneaker from '../components/Sneaker.vue';

import img1 from '../assets/sneakers-img1.svg';
import img2 from '../assets/sneakers-img2.svg';
import img3 from '../assets/sneakers-img3.svg';
import img4 from '../assets/sneakers-img4.svg';
import img5 from '../assets/sneakers-img5.svg';
import img6 from '../assets/sneakers-img6.svg';
import img7 from '../assets/sneakers-img7.svg';
import img8 from '../assets/sneakers-img8.svg';
import img9 from '../assets/sneakers-img9.svg';
import img10 from '../assets/sneakers-img10.svg';
import img11 from '../assets/sneakers-img11.svg';
import img12 from '../assets/sneakers-img12.svg';

import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';

const sneakers = [
  {
    id: 0,
    sneakersUrl: img1,
    title: 'Мужские Кроссовки Nike Blazer Mid Suede',
    price: 12999,
  },
  {
    id: 1,
    sneakersUrl: img2,
    title: 'Мужские Кроссовки Nike Air Max 270',
    price: 12999,
  },
  {
    id: 2,
    sneakersUrl: img3,
    title: 'Мужские Кроссовки Nike Blazer Mid Suede',
    price: 8499,
  },
  {
    id: 3,
    sneakersUrl: img4,
    title: 'Кроссовки Puma X Aka Boku Future Rider',
    price: 8999,
  },
  {
    id: 4,
    sneakersUrl: img5,
    title: 'Кроссовки Puma X Aka Boku Future Rider',
    price: 8999,
  },
  {
    id: 5,
    sneakersUrl: img6,
    title: 'Мужские Кроссовки Under Armour Curry 8',
    price: 15199,
  },
  {
    id: 6,
    sneakersUrl: img7,
    title: 'Мужские Кроссовки Nike Kyrie 7',
    price: 11299,
  },
  {
    id: 7,
    sneakersUrl: img8,
    title: 'Мужские Кроссовки Jordan Air Jordan 11',
    price: 10799,
  },
  {
    id: 8,
    sneakersUrl: img9,
    title: 'Мужские Кроссовки Nike LeBron XVIII',
    price: 16499,
  },
  {
    id: 9,
    sneakersUrl: img10,
    title: 'Мужские Кроссовки Nike Lebron XVIII Low',
    price: 13999,
  },
  {
    id: 10,
    sneakersUrl: img11,
    title: 'Мужские Кроссовки Nike Blazer Mid Suede',
    price: 8499,
  },
  {
    id: 11,
    sneakersUrl: img12,
    title: 'Кроссовки Puma X Aka Boku Future Rider',
    price: 11299,
  },
];

const liked = ref([]);
const cart = ref([]);

const addToLiked = (e) => {
  liked.value.push(e);
};

const removeFromLiked = (e) => {
  liked.value = liked.value.filter((item) => item.id !== e.id);
};

const addToCart = (e) => {
  cart.value.push(e);
}

const removeFromCart = (e) => {
  cart.value = cart.value.filter(item => item.id !==e.id);
}
</script>

<template>
  <Swiper
    :slides-per-view="1"
    :space-between="50"
    :pagination="{ clickable: true }"
  >
    <SwiperSlide>
      <div class="flex justify-center my-[45px]">
        <img src="../assets/slide-img.png" alt="" />
      </div>
    </SwiperSlide>
    <SwiperSlide>
      <div class="flex justify-center my-[45px]">
        <img src="../assets/slide-img.png" alt="" />
      </div>
    </SwiperSlide>
    <SwiperSlide>
      <div class="flex justify-center my-[45px]">
        <img src="../assets/slide-img.png" alt="" />
      </div>
    </SwiperSlide>
  </Swiper>

  <div class="">
    <div class="flex justify-between">
      <h2 class="font-bold text-[32px]">Все кроссовки</h2>
      <label
        for="search"
        class="flex gap-[13.75px] w-[250px] py-[13px] pl-[18px] rounded-[10px] border-gray-200 border-[1px]"
      >
        <img src="../assets/search.svg" alt="" />
        <input type="text" placeholder="Поиск..." id="search" />
      </label>
    </div>

    <div class="content grid grid-cols-4 gap-y-[40px] mt-[40px]">
      <Sneaker
        v-for="(sneaker, i) in sneakers"
        :key="i"
        :sneaker="sneaker"
        @jazgul="addToLiked"
        @anjelika="removeFromLiked"
        @addToCart="addToCart"
        @removeFromCart="removeFromCart"
      />
    </div>
  </div>
</template>
