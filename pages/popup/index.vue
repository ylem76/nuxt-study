<template>
  <div>
    <button @click="showModal = true">show modal</button>
    <basic-popup v-if="showModal" @close="closeModal"> </basic-popup>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showModal: false
    };
  },
  methods: {
    closeModal() {
      this.showModal = false;
    }
  }
};
</script>
