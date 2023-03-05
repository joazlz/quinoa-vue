<script setup lang="ts">
import { ref } from 'vue'
import axios from 'axios'

defineProps<{ msg: string }>();

const count = ref(0);


let info:string = "";

axios
  .get('http://localhost:8080/hello')
  .then(response => {
    info = response.data.bpi
  });
</script>

<template>
  <h1>{{ info }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      <code>HOLA ERICK</code>
    </p>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
