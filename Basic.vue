<template>
  <h1>{{ msg }}</h1>
  <h2 v-for="a in array" :key="a.id">{{ a }}</h2>
  <div class="content">

    <Chip :text="'Submit'" v-for="chip in chips"
          :key="chip" :chip="chip"
          @onClick="chip.id"
          @mouseleave="testLog"
          :active="chip.id===test"
          :prefix="chip.id"
          :suffix="chip.id"/>
  </div>
</template>

<script>
import Chip from "./Chip.vue";
export default {
  name: "Basic",
  components: {Chip},
  props: {
    msg: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      chips: [
        {id: 1, selected: false, selecte: false},
        {id: 2, selected: false, selecte: false},
        {id: 3, selected: false, selecte: false},
        {id: 4, selected: false, selecte: false},
      ],

    };
  },
  methods: {
    testLog(){
      console.log('work')
    },
    buttons(id) {
      this.chips.forEach(res => {
        res.selected = false
        res.selecte = false
      })
      if (id === 2) {
        this.chips.find(res => res.id === id).selected = false;
        this.chips.find(res => res.id === id).selecte = true;
      }
      if (id === 3) {
        this.chips.find(res => res.id === id).selected = true;
        this.chips.find(res => res.id === id).selecte = false;
      }
      if (id === 4) {
        this.chips.find(res => res.id === id).selected = true;
        this.chips.find(res => res.id === id).selecte = true;
      }
    },
  }
}
</script>

<style scoped>
.content {
  display: flex;
  gap: 1rem;
}

</style>
