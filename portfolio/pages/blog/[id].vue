<template>
  <div>
    <h1>You are looking at the {{ route.params.id }} blog.</h1>
  </div>
  <div>We are inside a blog!</div>
</template>

<script setup>
  const route = useRoute()
</script>
