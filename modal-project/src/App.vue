<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
  <h1>{{ people.firstName }}</h1>
  <div v-if="showModal">
    <Modal :age= people.age @close="toggleModal">
      <h1>This is my heading</h1>
      <p>This is my paragraph</p>
      <template v-slot:links>
        <a href="https://www.google.com/"> Sign Up</a>
        <a href="https://www.google.com/"> More Info</a>
      </template>
    </Modal>
  </div>
  <p>Welcome</p>
  <input type="text" ref="name">
  <button @click="toggleModal">Open Modal</button>

</template>

<script>
import Modal from './components/Modal.vue'
import Navbar from './components/Navbar.vue'
export default {
  name: 'App',
  components:{Modal, Navbar},
  data (){
    return{
      bodyText: 'This is some dummy text',
      people: {firstName:'My First Name',lastName:'My Last Name',age:20},
      showModal: false
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal
      this.$refs.name.focus();
    }
  }
}
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
h1{
  color: aqua;
}
</style>
