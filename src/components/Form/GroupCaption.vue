<template>
    <i :class="`dx-icon dx-icon-${icon}`"/><span>{{ data.caption }}</span>
  </template>
  <script setup lang="ts">
  
  withDefaults(defineProps<{
    data?: Record<string, any>
    icon?: string
  }>(), {
    data: () => ({} as Record<string, any>),
    icon: 'info',
  });
  </script>