<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name">
  <button @click="onclickHandler">Click</button> -->
  <teleport to=".modal" v-if="showModal">
    <!-- If we want to pass data from parent to child component we use props -->
    <!-- If we want to pass data through attributes, we have to bind it with v-bind: or : -->
    <Modal :theme="theme" @close="showModal = !showModal">
      <h1>{{ header }}</h1>
      <p>{{ content }}</p>
      <template v-slot:buttons>
        <div class="btns">
          <span class="no" @click="showModal = !showModal">NO</span>
          <span class="yes">YES</span>
        </div>
      </template>
    </Modal>
  </teleport>
  <button @click="showModal = !showModal">
    {{ showModal ? "Hide Modal" : "Show Modal" }}
  </button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  data() {
    return {
      title: "My Vue 3 Practise",
      header: "Log Out?",
      content: "Are you sure you want to Log Out?",
      theme: "danger",
      showModal: false,
    };
  },
  methods: {
    onclickHandler() {
      this.$refs.name.textContent = "Hello";
    },
  },
  components: {
    Modal,
  },
};
</script>

<style scoped>
p {
  font-style: normal;
}
.btns{
  display: flex;
  width: 100%;
}
span{
  transition: background 0.3s;
}
.no {
  flex: 1;
  padding: 10px 0px;
  background: gray;
  margin: 10px;
  color: white;
  border-radius: 10px;
  text-align: center;
}
.yes {
  text-align: center;
  padding: 10px 0px;
  flex: 1;
  width: 50px;
  background: gray;
  margin: 10px;
  color: white;
  border-radius: 10px;
  background-color: red;
}
.no:hover{
  cursor: pointer;
  background: rgb(111, 110, 110);
}
.yes:hover{
  cursor: pointer;
  background: rgb(239, 10, 10);
}
</style>
