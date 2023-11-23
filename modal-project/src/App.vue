<template>
  <h1>{{ people.firstName }}</h1>
  <Modal />
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button>

</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components:{Modal},
  data (){
    return{
      test: 'test',
      people: {firstName:'My First Name',lastName:'My Last Name',age:20}
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
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
</style>
