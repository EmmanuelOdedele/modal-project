<template>
  <h1>{{ title }}</h1>
  <br />
  <p class="welcome">Welcome</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <h1>Sign up to the newsletter</h1>
      <p>For updates and promo codes!</p>
      <template v-slot:book>
        <p>Book 1</p>
        <p>Book 2</p>
      </template>
    </Modal>
  </div>
  <button class="btn" @click="toggleModal">Open Modal</button>
  <br />
  <button class="btn" id="btn2" @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue App",
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
#app {
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
.welcome {
  font-style: normal;
}
.btn{
  border: none;
  height: 25px;
  background: #2c3e50;
  color: white;
  border-radius:5px;
  padding: 0 10px;
}
.btn:hover{
  background: #1c2733;
  cursor: pointer;
}
#btn2 {
  margin-top: 10px;
}
</style>
