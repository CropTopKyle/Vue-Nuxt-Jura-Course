<template>
  <div class="mb-10">
    <h1>Github Projects</h1>
  </div>
  <div>
    <section v-if="pending">Loading...</section>
    <section v-else-if="error">Something went wrong: {{ error }}</section>
    <section
      v-else="pending"
      class="grid grid-cols-1 gap-4">
      <ul>
        <li
          v-for="project in sortedProjects"
          :key="project"
          class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono dark:hover:bg-gray-700">
          <a
            :href="project.html_url"
            target="_blank">
            <div class="flex items-center justify-between text-sm">
              <div class="font-semibold">{{ project.name }}</div>
              <div class="font-semibold">{{ project.size }} ★</div>
            </div>
            <p class="text-sm">Last Updated: {{ project.updated_at }}</p>
          </a>
        </li>
      </ul>
    </section>
  </div>
</template>

<script setup>
  import { computed } from 'vue'

  const { error, pending, data } = await useFetch(
    'https://api.github.com/users/croptopkyle/repos'
  )

  const sortedProjects = computed(() =>
    data.value.filter((project) => project.size).sort((a, b) => b.size - a.size)
  )

  console.log(data)
</script>
