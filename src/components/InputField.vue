<script setup>
import { ref, watch } from "vue";

const input = ref("");
const words = ref(0);

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
  const splitStr = input.value.toLowerCase().split(" ");
  for (let i = 0; i < splitStr.length; i++) {
    splitStr[i] = splitStr[i].charAt(0).toUpperCase() + splitStr[i].substring(1);
  }
  return (input.value = splitStr.join(" "));
};

const clearField = () => {
  input.value = "";
};

watch(input, (str) => {
  words.value = str.trim().split(/\s+/).length;
});
</script>

<template>
  <div class="container">
    <p>{{ words }} Words</p>
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
