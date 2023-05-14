<script setup>
import VueDatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css'

import { ref } from 'vue';

const date = ref(new Date());
</script>

<template>
  <VueDatePicker
    v-model="date"
    locale="jp"
    select-text="選択"
    cancel-text="キャンセル"
    format="yyyy年MM月dd日"
    disable-month-year-select
    :clearable="false"
  >
    <!-- <template #input-icon>
        <img class="input-slot-image" src="../public/icon.png"/>
    </template> -->
  </VueDatePicker>
</template>

<style scoped>
:deep(.dp__input) {
  border-radius: 10px;
  border: 10px solid pink;
}
:deep(.dp__action_buttons) {
  flex: none;
}
:deep(.dp__input_icon) {
  right: 0;
  left: auto;
}
:deep(.dp__input_icon_pad) {
  padding-left: 8px;
}
.input-slot-image {
  height: 20px;
  width: auto;
  margin-left: 5px;
}
</style>
