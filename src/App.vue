<template>
  <h1>{{title}}</h1>
  <teleport to='.modals' v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">link one</a>
          <a href="#">link two</a>
        </template>
        <h1>This is the modal you been lookin' for</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi similique ab beatae ipsam dolor, facere earum mollitia? Nostrum quos autem quibusdam laboriosam? Aliquam officia rerum totam. Sequi hic maiores veritatis?</p>
    </Modal>
  </teleport><br>

<teleport to='.modals' v-if="showModal2">
    <Modal @close="toggleModal2">
        <h1>Sign up</h1>
        <p>Sequi hic maiores veritatis?</p>
    </Modal>
  </teleport><br>
  
  <button @click.alt="toggleModal">Show Modal (alt)</button>
  <button @click="toggleModal2">Show Modal Two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal},
  data() {
    return {
      title: "This is my first vue hehe :)",
      showModal: false,
      showModal2: false,
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2
    }
  },
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
h1{
  border-bottom: 1px solid black;
  display: inline-block;
  padding-top: 10px;
}
</style>
