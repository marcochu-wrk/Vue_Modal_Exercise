<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
  <h1>{{ welcome }}</h1>
  <teleport to="#modals" v-if="showModal">
    <Modal :age= person1.age @close="toggleModal">
      <h1>This is my heading</h1>
      <p>This is my paragraph</p>
      <template v-slot:links>
        <a href="https://www.google.com/"> Sign Up</a>
        <a href="https://www.google.com/"> More Info</a>
      </template>
    </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModal2">
    <Modal :age="person2.age" @close="toggleModal2">
      <h1>You clicked on the second heading</h1>
      <p>This is the second Modal</p>
    </Modal>
  </teleport>
  <p>Welcome</p>
  <input type="text" ref="name">
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Modal 2</button>
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
      welcome:'This is the test site',
      person1: {firstName:'My First Name',lastName:'My Last Name',age:20},
      person2: {firstName:'Another First Name',lastName:'Another Last Name',age:10},
      showModal: false,
      showModal2: false
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal;
      this.$refs.name.focus();
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2;
      this.$refs.name.focus();
    }
  }
}
</script>

<style>
#app, #modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  color: rgb(60, 50, 107);
}
</style>
