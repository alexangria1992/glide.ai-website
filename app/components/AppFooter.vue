<script lang="ts" setup>
import type {Content} from "@prismicio/client"
defineProps<{
  settings?: Content.SettingsDocument
}>()
</script>

<template>
  <footer>
    <nav
      aria-label="Footer"
      class="flex flex-col justify-between items-center gap-6 px-8 py-7 md:flex-row border-t border-gray-600"
    >
      <NuxtLink to="/" class="z-50">
        <GlideLogo />
        <span class="sr-only">{{ settings?.data.site_title }} home page</span>
      </NuxtLink>

      <!-- Desktop Nav -->
      <ul class=" flex gap-6">
        <li v-for="link in settings?.data.navigation" :key="link.key">
          <PrismicLink
            :field="link"
            class="inline-flex min-h-11 items-center"
          />
        </li>
      </ul>
    </nav>
  </footer>
</template>
