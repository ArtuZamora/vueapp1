<script setup>
  import Modal from '../components/Modal.vue'
  import { ref } from 'vue';

  const title = 'My First VueJS App :)';
  const modalVisible = ref(false);
  const showModal = () => {
    modalVisible.value = true;
  }
  const hideModal = () => {
    modalVisible.value = false;
  }
</script>

<template>
  <h1>{{ title }}</h1>
    <Modal header="Sign up for the Giveaway!" :body="{line1: 'Line1'}" theme="sale" :show="modalVisible" :hideFunction="hideModal" @close="hideModal">
      <template v-slot:links>
        <a href="#">More Info</a>
        <a href="#">Sign Up</a>
      </template>
      <div>
        SLOT COMPONENT
      </div>
    </Modal>
  <br>
  <button @click="showModal()">Show Modal</button>
</template>