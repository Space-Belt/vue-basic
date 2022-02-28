<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>

  <teleport to="#modals" v-if="showModal">
    <ModalPage theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>SpaceBelt Givaway</h1>
      <p>Space-belt Space-belt Space-belt Space-belt</p>
    </ModalPage>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
    <ModalPage @close="toggleModalTwo">
      <h1>SpaceBelt Givaway</h1>
      <p>Crucial-Sub Crucial-Sub Crucial-Sub Crucial-Sub Crucial-Sub</p>
    </ModalPage>
  </teleport>

  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click="toggleModalTwo">open modal 2</button>
</template>

<script>
import ModalPage from "./components/ModalPage.vue";

export default {
  name: "App",
  components: { ModalPage },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
#modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
