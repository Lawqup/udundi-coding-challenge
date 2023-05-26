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
  <div class="relative top-96 left-1/2 inline-block">
    <transition
      name="fade-down"
      appear-from-class="-translate-y-20 opacity-0"
      appear
    >
      <h1
        class="font-didot text-[15rem] font-light overflow-hidden explore"
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
        class="font-lato text-2xl font-light relative -top-16 flex items-center transition-all ease-in-out delay-500 duration-500"
      >
        <img
          class="float-left mr-6 relative"
          src="../Coding Challenge Assets/Plus.svg"
          @click="detailsEnter"
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
  transition: all 0.3s ease-in-out;
}

.modal.show {
  width: 580px;
  height: 690px;
  border-radius: 0%;
  opacity: 1;
}

.explore {
  transition: opacity 1s ease-in-out, transform 1s ease-in-out,
    background-position 0.3s ease-in-out;
  background: linear-gradient(to left, white 34%, transparent 65%) right;
  background-size: 300% 100%;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.explore.hide {
  background-position: left;
}
</style>
