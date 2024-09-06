<template>
  <div class="bckdrop" @click.self="closeModal">
    <div class="modal" :class="{ success: theme === 'success', danger: theme === 'danger' }">
      <!-- if we want to pass html template, we use slot -->
      <slot> Default </slot>
      <slot name="buttons" />
    </div>
  </div>
</template>

<script>
export default {
  /**
   * Props are used to pass data from parent to child component
   */
  props: ["theme"],
  methods: {
    closeModal() {
      /**
       * If we want to change sth in parent, we can emit an event which will be use in parent component
       */
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.bckdrop {
  position: fixed;
  background-color: rgba(0, 0, 0, 0.5);
  top: 0;
  width: 100%;
  height: 100%;
}

.modal {
  margin: 100px auto;
  background-color: white;
  width: 400px;
  padding: 20px;
  border-radius: 10px;
}

p {
  font-style: normal;
}

.success {
  background-color: white;
  color: black;
}

.danger {
  background-color: white;
  color: black;
}
</style>
