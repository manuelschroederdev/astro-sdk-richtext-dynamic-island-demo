<script setup>
import { computed } from 'vue'
import { renderRichText } from '@storyblok/astro'
const props = defineProps({ blok: Object })
const renderedRichText = computed(() => renderRichText(props.blok?.richtext))
</script>

<template>
  <div class="container">
    <h3 class="mb-8 text-6xl text-[#50b0ae] font-bold">{{ blok.headline }}</h3>
    <div class="prose" v-html="renderedRichText" />
  </div>
</template>
