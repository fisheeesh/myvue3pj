<template>
  <div class="bckdrop">
    <div class="modal" :class="{success:theme==='success', danger:theme === 'danger'}">
      <h1>{{header}}</h1>
      <p>{{content}}</p>
    </div>
  </div>
</template>

<script>
export default {
  props:[
    'header',
    'content',
    'theme'
  ]
}
</script>

<style scoped>
.bckdrop{
  position: fixed;
  background-color: rgba(0, 0, 0,0.5);
  top: 0;
  width: 100%;
  height: 100%;
}
.modal{
  margin: 100px auto;
  background-color: white;
  width: 400px;
  padding: 20px;
  border-radius: 10px;
}
p{
  font-style: normal;
}
.success{
  background-color: green;
  color: white;
}
.danger{
  background-color: crimson;
  color: white;
}
</style>