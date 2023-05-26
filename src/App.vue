<script>
import Explore from "./Explore.vue";
export default {
  data() {
    return {
      loaded: false,
    };
  },
  components: {
    Explore,
  },
};
</script>

<template>
  <div class="flex h-screen justify-items-end text-white">
    <div class="bg-primary-brown w-0 md:w-[30rem] z-10">
      <Explore />
    </div>
    <transition name="fade" enter-active-class="opacity-0">
      <img
        class="object-cover w-full transition-all ease-in-out duration-500"
        v-show="loaded"
        @load="loaded = true"
        id="img-background"
        src="@/Coding_Challenge_Assets/Coding-Challenge-Image.png"
      />
    </transition>
  </div>
  <div class="absolute bottom-0 right-0 mb-12 mr-8">
    <img
      class="mb-6 hover:opacity-75 transition-opacity duration-200"
      src="@/Coding_Challenge_Assets/Facebook.svg"
    />
    <img
      class="hover:opacity-75 transition-opacity duration-200"
      src="@/Coding_Challenge_Assets/Instagram.svg"
    />
  </div>
</template>

<style scoped></style>
