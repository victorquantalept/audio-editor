<template>
  <v-text-field
    :label="label"
    :model-value="modelValue" 
    density="compact"
    variant="plain"
    style="border-radius: 5px;background-color: #e6e6ff; height: 45px;"
    class="mt-3 text-center"
  ></v-text-field>
</template>

<script lang="ts">
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'audioTextField',
  props: {
    label: {
      type: String,
      required: true,
    },
    modelValue: {
      type: String,
      required: true, 
    },
  },
});
</script>
