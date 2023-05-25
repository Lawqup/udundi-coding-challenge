<script>
export default {
  data() {
    return {
      showDetails: false,
    };
  },
};
</script>

<template>
  <div class="relative top-96 left-1/2 w-full">
    <transition
      name="fade-down"
      appear-active-class="-translate-y-20 opacity-0"
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
      appear-active-class="-translate-x-20 opacity-0"
      appear
    >
      <span
        class="font-lato text-2xl font-light relative -top-16 flex items-center transition-all ease-in-out delay-500 duration-500"
      >
        <img
          class="float-left mr-6"
          src="../Coding Challenge Assets/Plus.svg"
          @click="showDetails = true"
        />
        More Details
      </span>
    </transition>
    <div
      class="relative bg-white w-[580px] h-[690px] -translate-y-full -translate-x-10 flex flex-col items-end"
      v-if="showDetails"
    >
      <span
        class="w-12 flex items-center text-center text-6xl font-light text-primary-brown text-black"
        @click="showDetails = false"
        >&times;</span
      >
      <div class="my-6 mx-20">
        <h2 class="text-primary-brown text-6xl font-didot font-light mb-6">
          Explore
        </h2>
        <p class="font-lato text-gray-900 text-base">
          Sed ut perspiciatis unde omnis iste natus error sit voluptatem
          accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae
          ab illo inventore veritatis et quasi architecto beatae vitae dicta
          sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
          aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos
          qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui
          dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed
          quia non numquam eius modi tempora incidunt ut labore et dolore magnam
          aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum
          exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex
          ea commodi consequatur?
        </p>
        <button
          class="font-lato font-light text-lg inline-block w-60 h-14 mt-12 bg-gradient-to-r from-primary-brown to-secondary-brown"
        >
          READ MORE
        </button>
      </div>
    </div>
  </div>
</template>
