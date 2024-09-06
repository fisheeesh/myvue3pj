<template>
  <h1>{{title}}</h1>
  <!-- <input type="text" ref="name">
  <button @click="onclickHandler">Click</button> -->
  <div v-if="showModal">

    <!-- If we want to pass data from parent to child component we use props -->
    <!-- If we want to pass data through attributes, we have to bind it with v-bind: or : -->
    <Modal :header="header" :content="content" :theme="theme" @close="showModal = !showModal"/>
  </div>
  <button @click.right="showModal = !showModal">{{ showModal ? 'Hide Modal' : 'Show Modal' }}</button>
</template>

<script>
import Modal from './components/Modal.vue'
export default {

  data(){
    return{
      title : 'My Vue 3 Practise',
      header: 'Login Success',
      content: 'Welcome to our website',
      theme: 'success',
      showModal : false
    }
  },
  methods:{
    onclickHandler(){
      this.$refs.name.textContent = 'Hello'
    }
  },
  components:{
    Modal
  }
}
</script>

<style scoped>

</style>