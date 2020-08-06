<template>
  <div class="modal">
    <div class="modal-overlay"></div>
    <div class="modal-inner">
        <slot></slot>
    </div>
  </div>
</template>
<style scoped>
.modal { 
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: 100;
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-overlay {
    background: rgba(0,0,0,0.8);
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: 101;
}
.modal-inner {
    background: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 575px;
    height: 525px;
    z-index: 101;
    flex-flow: column;
}
</style>