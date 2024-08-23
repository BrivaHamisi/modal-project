<template>
  <h1>{{title}}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">More Info</a>
      </template>
      <h1> Ninja Giveaway</h1>
      <p> Grab your Ninja Swag for half Price</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal  @close="toggleModalTwo">
      <h1> Sign Up for the Newsletters</h1>
      <p> For Updates and promo Codes!</p>
    </Modal>
  </div>
  
  <button @click="showModal = true">Show Modal</button>
  <button @click="showModalTwo = true">Show Modal Two</button>
</template>

<script>
import Modal from "./components/Modal.vue"

export default {
  name: 'App',
  components:{Modal},
  data(){
    return{
      title: 'My First Vue Project :)',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods:{
    toggleModal(){
      this.showModal =!this.showModal;
    },
    toggleModalTwo(){
      this.showModalTwo =!this.showModalTwo;
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
