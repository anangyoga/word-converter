<script setup>
import { ref } from "vue";

const input = ref("");

const handleLowerCase = () => {
  input.value = input.value.toLowerCase();
};
const handleUpperrCase = () => {
  input.value = input.value.toUpperCase();
};

const handleSentenceCase = () => {
  const firstLetter = input.value[0];
  const upperCase = firstLetter.toUpperCase();
  const slice = input.value.slice(1);
  return (input.value = upperCase + slice.toLowerCase());
};

const handleTitleCase = () => {
  const charAt = input.value.charAt(0);
  console.log(charAt);
};

const clearField = () => {
  input.value = "";
};
</script>

<template>
  <div class="container">
    <p>150 Words</p>
    <textarea v-model="input" name="fields" id="note" cols="60" rows="20"> </textarea>
    <div class="buttons">
      <button @click="handleSentenceCase">Sentence Case</button>
      <button @click="handleLowerCase">lower case</button>
      <button @click="handleUpperrCase">UPPER CASE</button>
      <button @click="handleTitleCase">Title Case</button>
      <button @click="clearField">Clear</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  margin-top: 25px;
}

.container p {
  margin-left: 800px;
}
textarea {
  border-radius: 15px;
  padding: 10px;
  width: 900px;
  overflow: hidden;
  outline: none;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 5px;
}

.buttons button {
  cursor: pointer;
}
</style>
