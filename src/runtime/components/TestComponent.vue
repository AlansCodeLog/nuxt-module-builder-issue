<template>
  <!-- eslint-disable @stylistic/no-tabs -->
  <button
    :class="!($attrs as any).unstyle"
    :type="$attrs.type as any"
    :tabindex="0"
    :data-color="color"
    v-bind="{
      ...$attrs,
      class: undefined,
    }"
  />
</template>

<script setup  lang="ts">
import { useAttrs } from 'vue'
import { propDefaults } from '../defaults.js'

const $attrs = useAttrs()

defineOptions({
  name: 'LibButton',
})

withDefaults(defineProps<{
  color?: string
  disabled?: boolean
}>(), {
  color: 'blue',
  ...propDefaults,
})
</script>

<script lang="ts">
</script>
