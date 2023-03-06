<script setup lang="ts">
import {ref} from 'vue'
import Basic from "./Basic.vue";
import Buttons from "./Buttons.vue";


let defineConfig1 = defineConfig({
  chips: [
    {id: 1, selected: false},
    {id: 2, selected: false},
    {id: 3, selected: false},
  ]
})
export default defineConfig1



defineProps<{ value: string }>()

const count = ref(0)



</script>

<template>
  <h1>{{ value }}</h1>

  <div>
    <div class="content">
      <Basic
          v-for="chip in chips" :key="chip" :chip="chip" @onClick="setActiveChip" :suffix="chip.selected"
      />
    </div>
    <Buttons/>
  </div>
</template>

<style scoped>
h1 {
  margin-bottom: 20px;
}

.content {
  display: flex;
  gap: 4rem;
}


</style>