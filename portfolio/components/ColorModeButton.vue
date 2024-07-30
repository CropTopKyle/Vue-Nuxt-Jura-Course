<template>
  <div>
    <button @click="toggleMode">Change Theme</button>
  </div>
</template>
<script setup>
  const colorMode = useColorMode()
  const modes = ['system', 'light', 'dark']

  const nextMode = computed(() => {
    const currentModeIndex = modes.indexOf(colorMode.preference)
    const nextModeIndex =
      currentModeIndex + 1 === modes.length ? 0 : currentModeIndex + 1
    return modes[nextModeIndex]
  })

  const toggleMode = () => {
    colorMode.preference = nextMode.value
  }
</script>
<style></style>
