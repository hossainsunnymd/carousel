<script setup>
import { ref, reactive } from "vue";

const image = ref(
  "https://images.unsplash.com/photo-1732719812776-c043e861faf8?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw3fHx8ZW58MHx8fHx8"
);
const carousels = reactive([
  {
    thumb:
      "https://images.unsplash.com/photo-1732719812776-c043e861faf8?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw3fHx8ZW58MHx8fHx8",
    full: "https://images.unsplash.com/photo-1732719812776-c043e861faf8?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw3fHx8ZW58MHx8fHx8",
  },
  {
    thumb:
      "https://images.unsplash.com/photo-1674803335439-7e8b843c6d4e?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw4fHx8ZW58MHx8fHx8",
    full: "https://images.unsplash.com/photo-1674803335439-7e8b843c6d4e?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw4fHx8ZW58MHx8fHx8",
  },
  {
    thumb:
      "https://images.unsplash.com/photo-1732204132499-6f208b7c4cb6?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw5fHx8ZW58MHx8fHx8",
    full: "https://images.unsplash.com/photo-1732204132499-6f208b7c4cb6?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw5fHx8ZW58MHx8fHx8",
  },
]);

function setImage(data) {
  image.value = data.full;
}
</script>

<template>
  <div :class="`flex justify-center mt-5 gap-5`">
    <div v-for="(carousel, index) in carousels" :key="index">
      <img
        @click="setImage(carousel)"
        :src="carousel.full"
        class="block w-[200px] h-[200px]"
      />
    </div>
  </div>

  <div class="flex justify-center h-[500px] mt-10">
    <img :src="image" height="full" width="1000px" />
  </div>
</template>

<style scoped></style>
