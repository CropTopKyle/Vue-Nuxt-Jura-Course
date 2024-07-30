<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center mt-5">
      <div>
        <NuxtLink
          to="/"
          class="p-1 text-xl font-semibold"
          >Blog</NuxtLink
        >
      </div>

      <div>
        <TheTopMenu />
      </div>

      <div>
        <ColorModeButton />
      </div>
    </header>
    <main class="p-2 mt-10">
      <slot />
    </main>
  </div>
</template>

<script setup></script>

<style>
  body {
    @apply rounded-lg px-6 py-8;
  }

  .light {
    @apply bg-white;
  }

  .dark {
    @apply bg-slate-800 text-white;
  }
</style>
