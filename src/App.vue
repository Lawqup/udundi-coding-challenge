<script>
export default {
  data() {
    return {
      loaded: false,
    };
  },
  methods: {
    onLoaded() {
      this.loaded = true;
    },
  },
};
</script>

<template>
  <div class="flex h-screen justify-items-end text-white">
    <div class="bg-primary-brown w-[30rem] z-10">
      <div class="relative top-96 left-1/2 w-full">
        <transition
          name="fade-down"
          enter-active-class="-translate-y-20 opacity-0"
          appear
        >
          <h1
            class="font-didot text-[15rem] font-light transition-all ease-in-out duration-1000"
          >
            Explore
          </h1>
        </transition>
        <transition
          name="fade-right"
          enter-active-class="-translate-x-20 opacity-0"
          appear
        >
          <span
            class="font-lato text-2xl font-light relative -top-16 flex items-center transition-all ease-in-out delay-500 duration-500"
          >
            <img
              class="float-left mr-6"
              src="../Coding Challenge Assets/Plus.svg"
            />
            More Details
          </span>
        </transition>
      </div>
    </div>
    <transition name="fade" enter-active-class="opacity-0">
      <img
        class="object-cover bg-primary-brown w-full transition-all ease-in-out duration-500"
        v-show="loaded"
        @load="onLoaded"
        id="img-background"
        src="../Coding Challenge Assets/Coding-Challenge-Image.png"
      />
    </transition>
  </div>
  <div class="absolute bottom-0 right-0 mb-12 mr-8">
    <img class="mb-6" src="../Coding Challenge Assets/Facebook.svg" />
    <img class="" src="../Coding Challenge Assets/Instagram.svg" />
  </div>
</template>

<style scoped></style>
