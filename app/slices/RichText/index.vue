<script setup lang="ts">
import type { Content } from '@prismicio/client'

// The array passed to \`getSliceComponentProps\` is purely optional.
// Consider it as a visual hint for you when templating your slice.
defineProps(getSliceComponentProps<Content.RichTextSlice>(
  ['slice', 'index', 'slices', 'context']
));
</script>

<template>
  <section>
    <PrismicRichText
      :field="slice.primary.content"
      class="richtext"
      wrapper="section"
    />
  </section>
</template>

<style scoped>
section:deep(.richtext) {
  max-width: 600px;
  margin: 6em auto;

}

section:deep(.richtext .codespan) {
  font-family: monospace;
}
</style>
