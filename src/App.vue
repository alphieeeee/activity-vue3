<template>
  <button class="btn-one" @click="toggleModalOne">Open modal one</button>
  <button class="btn-two" @click="toggleModalTwo">Open modal two</button>
  <transition name="fade">
    <teleport to="#modal-wrapper">
      <modal v-if="modalOpenOne">
        <modal-one @close1="toggleModalOne"></modal-one>
      </modal>
    </teleport>
  </transition>
  <transition name="fade">
    <teleport to="#modal-wrapper">
      <modal v-if="modalOpenTwo" >
        <modal-two @close2="toggleModalTwo"></modal-two>
      </modal>
    </teleport>
  </transition>
</template>

<script>
import { ref } from 'vue'
import Modal from "./Modal.vue"
import ModalOne from "./ModalOne.vue"
import ModalTwo from "./ModalTwo.vue"

export default {
  components: { Modal, ModalOne, ModalTwo },
  emits: [ "close-one", "close-two" ],
  setup() {
    const modalOpenOne = ref(false)
    const modalOpenTwo = ref(false)
    const toggleModalOne = () => {
      modalOpenOne.value = !modalOpenOne.value;
      console.log(modalOpenOne.value)
    };
    const toggleModalTwo = () => {
      modalOpenTwo.value = !modalOpenTwo.value;
    };

    return {
      modalOpenOne,
      modalOpenTwo,
      toggleModalOne,
      toggleModalTwo
    }
  }
}
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-active {
  opacity: 0;
}
.btn-one {
  color: blue;
  margin-left: 1rem;
  margin-right: 1rem;
}
.btn-two {
  color: green;
  margin-left: 1rem;
  margin-right: 1rem;
}
</style>
