<script>
import Modal from "./Modal.vue";

export default {
  data() {
    return {
      showDetails: false,
    };
  },
  components: {
    Modal,
  },
  methods: {
    detailsEnter() {
      this.showDetails = true;
    },
    detailsLeave() {
      this.showDetails = false;
    },
  },
};
</script>

<template>
  <div class="relative top-[32rem] left-1/2 inline-block pl-4 md:pl-0">
    <transition
      name="fade-down"
      appear-from-class="-translate-y-20 opacity-0"
      appear
    >
      <h1
        class="font-didot text-8xl md:text-[15rem] font-light explore h-32 md:h-72"
        :class="{ hide: showDetails }"
      >
        Explore
      </h1>
    </transition>
    <transition
      name="fade-right"
      appear-from-class="-translate-x-20 opacity-0"
      appear
    >
      <span
        class="font-lato text-2xl font-light relative -top-4 md:-top-12 flex items-center transition-all ease-in-out delay-500 duration-500"
      >
        <img
          class="float-left mr-6 relative hover:opacity-75 transition-opacity duration-200"
          src="@/Coding_Challenge_Assets/Plus.svg"
          @click="detailsEnter"
          :class="{ compress: showDetails }"
        />
        More Details
      </span>
    </transition>
    <Modal
      @exit="detailsLeave"
      class="modal"
      :class="{ show: showDetails }"
      :show="showDetails"
    />
  </div>
</template>

<style>
.modal {
  width: 0;
  height: 0;
  border-radius: 100%;
  opacity: 0;
  transition: all 0.3s 0.3s ease-in-out;
}

@media (min-width: 768px) {
  .modal.show {
    width: 580px;
    height: 690px;
    border-radius: 0%;
    opacity: 1;
  }
}

@media (max-width: 768px) {
  .modal.show {
    width: 100vw;
    height: 100vh;
    border-radius: 0%;
    opacity: 1;
  }
}

.explore {
  transition: opacity 1s ease-in-out, transform 1s ease-in-out,
    background-position 0.5s 0.3s ease-in-out;
  background: linear-gradient(to left, white 35%, transparent 65%) right;
  background-size: 300% 100%;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.explore.hide {
  background-position: left;
}

@keyframes compressAnim {
  0% {
    transform: scale(100%);
  }
  50% {
    transform: scale(60%);
  }
  100% {
    transform: scale(100%);
  }
}

.compress {
  animation-name: compressAnim;
  animation-duration: 0.3s;
}
</style>
