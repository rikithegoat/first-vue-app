<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals" v-if="showModal">
    <myModal theme='sale' @close='toggleModal'>
      <template v-slot:links>
        <a href="">sign up now</a>
        <a href="">forgot your password?</a>
      </template>
      <h1>Free Giveaway today!</h1>
      <p>Grab now or never!</p>
    </myModal>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <myModal @close='toggleModalTwo'>
      <h1>Free Giveaway today!</h1>
      <p>Grab now or never!</p>
    </myModal>
  </teleport>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal 2</button>
</template>

<script>
import myModal from './components/myModal.vue'

export default {
  name: 'App',
  components: {myModal},
  data(){
    return{
      title: "My Frist Vue app",
      showModal: false,
      showModalTwo: false
    }
  },
  methods:{
    toggleModal(){
      this.showModal= !this.showModal;
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo;
    }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
