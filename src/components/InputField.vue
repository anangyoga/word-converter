<script setup></script>

<template>
  <div class="container">
    <p>150 Words</p>
    <textarea name="fields" id="note" cols="60" rows="20"> </textarea>
    <div class="buttons">
      <button>Capitalize</button>
      <button>lower case</button>
      <button>UPPER CASE</button>
      <button>Sentence case</button>
      <button>Clear</button>
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
