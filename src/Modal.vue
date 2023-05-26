<script>
export default {
  methods: {
    exit() {
      this.$emit("exit");
    },
  },
  props: ["show"],
};
</script>

<template>
  <div
    class="absolute bg-white -translate-y-full -translate-x-10 overflow-hidden"
  >
    <transition enter-from-class="opacity-0 -translate-x-10">
      <div
        class="flex flex-col items-end absolute transition transition-all duration-500 ease-in-out delay-700"
        v-if="show"
      >
        <button
          class="w-12 flex items-center text-center text-6xl font-light text-primary-brown text-black hover:opacity-75 transition-opacity duration-200"
          @click="exit"
        >
          &times;
        </button>
        <div class="my-6 mx-20">
          <h2 class="text-primary-brown text-6xl font-didot font-light mb-6">
            Explore
          </h2>
          <p class="font-lato text-gray-900 text-base">
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem
            accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
            quae ab illo inventore veritatis et quasi architecto beatae vitae
            dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
            aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
            eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est,
            qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit,
            sed quia non numquam eius modi tempora incidunt ut labore et dolore
            magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis
            nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut
            aliquid ex ea commodi consequatur?
          </p>
          <button
            class="font-lato font-light text-lg inline-block w-60 h-14 mt-12 bg-gradient-to-r from-primary-brown to-secondary-brown hover:opacity-75 transition-opacity duration-200"
          >
            READ MORE
          </button>
        </div>
      </div>
    </transition>
  </div>
</template>
