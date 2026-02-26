<script setup>
import { ref, reactive } from 'vue'

// ref
const message = ref('Hello vue!');
console.log(message.value);

// reactive
const user = reactive({
  name: 'John',
})
user.name = "rahul"

// function 
function changename() {
  if (message.value === "Hello vue!") {
    message.value = "Nitin"
  } else {
    message.value = "Hello vue!"
  }
}

const counter = ref(0);

const intervalId = setInterval(function () {
  counter.value++;
}, 1000);

setTimeout(() => {
    clearInterval(intervalId);
    counter.value= "Time over go for the lunch";
}, 5000);

</script>

<template>
  <h1>You did it!</h1>
  <p>
    {{ user.name }}
  </p>

  <div class="border boder-3 p-3 flex flex-col w-1/8 gap-4 m-2">
    <p>
      {{ message }}
    </p>
    <button @click="changename" class="bg-gray-400 rounded-md px-4">Click</button>
  </div>

  <div>
    <p class="px-2">{{ counter }}</p>
  </div>
</template>

<style scoped></style>
