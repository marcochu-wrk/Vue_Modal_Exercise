<template>
  <h1>{{ people.firstName }}</h1>
  <div v-if="showModal">
    <Modal :header=people.lastName :text=bodyText :age= people.age @close="toggleModal" />
  </div>
  <p>Welcome</p>
  <input type="text" ref="name">
  <button @click="toggleModal">Open Modal</button>

</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components:{Modal},
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
