<template>
  <div class="bckdrop">
    <div class="modal">
      <h1>Modal Title</h1>
      <p>Modal Content</p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.bckdrop {
  position: fixed;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}
.modal {
  background-color: white;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  border-radius: 10px;
}
p {
  font-style: normal;
}
</style>
