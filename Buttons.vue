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

<script setup>
import {ref} from 'vue'
import Basic from "./Basic.vue";
import Buttons from "./Buttons.vue";
export default {

  data() {
    return {
      chips: [
        {id: 1, selected: false},
        {id: 2, selected: false},
        {id: 3, selected: false}
      ]
    };
  },
  methods: {
    setActiveChip(id) {
      this.chips.forEach(res => {
        res.selected = false
      })
      this.chips.find(res => res.id === id).selected = true;
    }
  },

}


</script>