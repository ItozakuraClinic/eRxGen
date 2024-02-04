<script setup lang="ts">
const props = defineProps({
  len: {
    type: String,
    default: "5"
  }
})
const lenOfContent = parseInt(props.len)
</script>

<template>
  <span>
    {{ "&nbsp;".repeat(lenOfContent) }}
  </span>
</template>
