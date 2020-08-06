<template>
  <div class="modal-content">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      <button @click="$emit('close2')">Dismiss</button>
  </div>
</template>
<style scoped>
.modal-content {
    position: relative;
    padding: 3rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: column;
}
p, button {
    color: green;
}
</style>