<template>
  <div>
    <DarkModeTest></DarkModeTest>
    <Tareas></Tareas>
  </div>
</template>

<script>
import DarkModeTest from "./components/DarkModeTest"
import Tareas from "./components/Tareas"

export default {
  name: 'App',
  components: {
    DarkModeTest,
    Tareas
  }
}
</script>

<style>
</style>
