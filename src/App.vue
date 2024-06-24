<script setup>
import { ref } from 'vue';

const inputValue = ref('');
const isRed = ref(false);

const handleChange = (event) => {
  inputValue.value = event.target.value;
};

const handleClick = () => {
  isRed.value = !isRed.value;
};
</script>

<template>
  <div class="tugas2">
    <span class="judul">TUGAS 2</span>
    <p>Ketika lebih dari 10 tulisan membesar</p>
    <input style="margin-bottom: 10px ; border-radius: 10px; font-size: 25px;" type="text" v-model="inputValue" @input="handleChange" />
    <div style="margin-bottom: 20px;" :class="{ 'red-text': inputValue.length > 5 }" :style="{ fontSize: inputValue.length > 10 ? '24px' : '16px', backgroundColor: inputValue}">
      {{ inputValue }}
    </div>
    <button @click="handleClick" :style="{ backgroundColor: isRed ? 'red' : '#007bff' }">Tekan Tombol</button>
  </div>
</template>

<style scoped>
.red-text {
  color: red;
}

.judul {
  font-size: 50px;
  margin-bottom: 20px;
  display: block;
  font-weight: bold;
}

.tugas2 {
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 100px;
}

.tugas2:hover {
  transform: scale(1.05);
  background-color:aliceblue
}

button {
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
}

button:hover {
  opacity: 0.8;
  transform: scale(1.1);
}

</style>
