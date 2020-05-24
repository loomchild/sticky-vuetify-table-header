<template>
  <v-app>
    <main-bar />
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script>
import MainBar from '@/components/MainBar'

export default {
  components: {
    MainBar
  }
}
</script>

<style scoped>
</style>
