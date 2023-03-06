<script setup>
defineProps({
  chip: {
    type: Object,
    required: true
  },
  prefix: {
    type: Boolean,
    required: false,
    default: false
  },
  suffix: {
    type: Boolean,
    required: false,
    default: false
  },
  tabindex: {
    type: Number,
    required: false,
    default: 1
  }
})

</script>

<template>
  <div class="content">
    <div @click="$emit('onClick',chip.id)"
         :class="{ active: 'active' }"
         :tabindex="tabindex">
      <div class="icon" v-if="prefix">
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 96 960 960" width="24" fill="red">
          <path
              d="M237 771q54-38 115.5-56.5T480 696q66 0 127.5 18.5T723 771q35-41 52-91t17-104q0-129.675-91.23-220.838Q609.541 264 479.77 264 350 264 259 355.162 168 446.325 168 576q0 54 17 104t52 91Zm243-123q-60 0-102-42t-42-102q0-60 42-102t102-42q60 0 102 42t42 102q0 60-42 102t-102 42Zm.276 312Q401 960 331 930q-70-30-122.5-82.5T126 725.042q-30-69.959-30-149.5Q96 496 126 426.5t82.5-122Q261 252 330.958 222q69.959-30 149.5-30Q560 192 629.5 222t122 82.5Q804 357 834 426.724q30 69.725 30 149Q864 655 834 725q-30 70-82.5 122.5T629.276 930q-69.725 30-149 30ZM480 888q52 0 100-16.5t90-48.5q-43-27-91-41t-99-14q-51 0-99.5 13.5T290 823q42 32 90 48.5T480 888Zm0-312q30 0 51-21t21-51q0-30-21-51t-51-21q-30 0-51 21t-21 51q0 30 21 51t51 21Zm0-72Zm0 319Z"/>
        </svg>
      </div>
      <div
      > {{ text }}
        <div class="icon" v-if="suffix">
          <svg xmlns="http://www.w3.org/2000/svg" height="15" viewBox="0 96 960 960" width="15" fill="#00a  153">
            <path
                d="m249 849-42-42 231-231-231-231 42-42 231 231 231-231 42 42-231 231 231 231-42 42-231-231-231 231Z"/>
          </svg>
        </div>
      </div>
    </div>

  </div>

</template>

<style scoped>
.chip {
  background-color: #F2F3F5;
  border: 1px solid rgba(35, 54, 45, 0.12);
  border-radius: 8px;
  display: flex;
  flex-direction: row;
  height: 32px;
  align-items: center;
  width: fit-content;
  padding: 0 12px;
  cursor: pointer;
  font-weight: 500;
  font-size: 14px;
  color: black;
}

.chip:focus {
  background: rgba(35, 54, 45, 0.12);
  border: 1px solid #00A153;
}

.chip:hover {
  background-color: rgba(35, 54, 45, 0.08);
}

.active {
  background-color: rgba(0, 161, 83, 0.04);
}

.content {
  display: flex;
}

.text {
  display: flex;
  align-items: center;
}

.icon {
  margin-left: 11px;
  display: flex;
  align-items: center;
  color: #23362D;
}

.svg {
  display: flex;
  align-items: center;
  margin-right: 8px;
}
</style>