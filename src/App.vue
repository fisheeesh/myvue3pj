<template>
  <h1 ref="greet">{{ title }}</h1>
  <button @click="onClickHandler">Click</button>
  <Modal/>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  data(){
    return{
      title : 'Hello World'
    }
  },
  methods:{
    onClickHandler(){
      this.$refs.greet.textContent = 'Hello!'
    }
  },
  components:{
    Modal
  }
};
</script>

<style scoped>
h1{
  color:red;
}
</style>