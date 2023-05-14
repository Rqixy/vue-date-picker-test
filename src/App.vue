<script setup>
import VueDatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css'

import { ref } from 'vue';
import { format } from 'date-fns'

const date = ref(new Date());
const formatDate = (date) => {
  return format(date, 'yyyy/M/d')
}
</script>

<template>
  <VueDatePicker
    v-model="date"
    locale="jp"
    select-text="選択する"
    cancel-text="キャンセル"
    :enable-time-picker="false"
    :format="formatDate"
    :clearable="false"
    :min-date="new Date()"
    no-today
  >
    <template #input-icon>
        <img class="input-slot-image" src="../public/calendar.svg"/>
    </template>
  </VueDatePicker>
</template>

<style scoped>
:deep(.dp__input) {
  border-radius: 10px;
  border: 2px solid gray;
}
:deep(.dp__action_buttons) {
  flex: none;
}
:deep(.dp__input_icon) {
  top: 60%;
  right: 16px;
  left: auto;
}
:deep(.dp__input_icon_pad) {
  padding-left: 8px;
}
.input-slot-image {
  height: 24px;
  width: auto;
  filter: invert(50%) sepia(0%) hue-rotate(231deg) brightness(0%) contrast(100%);
}
</style>
