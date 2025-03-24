<script setup>
import { defineEmits } from 'vue';

const props = defineProps({
  isVisible: {
    type: Boolean,
    required: true,
  }
});
const emit = defineEmits(['close']);

const closeModal = () => emit('close');
</script>

<template>
    <div v-if="isVisible" class="modal" @click.self="closeModal">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <slot></slot>
      </div>
    </div>
</template>
  
<style>
.modal {
  display: flex; 
  justify-content: center; 
  align-items: center; 
  position: fixed; 
  z-index: 9989; 
  left: 0;
  top: 0;
  width: 100%; 
  height: 100%; 
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background: linear-gradient(#221F31, #6747e8);
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 500px;
  height: 360px;
  text-align: center;
}

.close {
  color: #aaa;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
  float: right;
}

.close:hover {
  color: black;
}
</style>