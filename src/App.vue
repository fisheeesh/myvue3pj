<template>
  <h1>{{title}}</h1>
  <input type="text" ref="name">
  <button @click="onclickHandler">Click</button>
  <Modal :header="header" :content="content" :theme="theme"/>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  data(){
    return{
      title : 'My Vue 3 Practise',
      header: 'Login Success',
      content: 'Welcome to our website',
      theme: 'success'
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