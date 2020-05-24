<template>
  <v-app-bar ref="toolbar" v-mutate="onMutate" color="teal darken-3" app dark shrink-on-scroll prominent scroll-threshold="400">
    <v-app-bar-nav-icon />
    <v-toolbar-title>Sticky Table Headers Demo</v-toolbar-title>
    <v-spacer />
  </v-app-bar>
</template>

<script>
export default {
  methods: {
    onMutate () {
      let height = 0
      const toolbar = this.$refs.toolbar
      if (toolbar) {
        height = `${toolbar.$el.offsetHeight}px`
      }
      document.documentElement.style.setProperty('--mainBarHeight', height)
    }
  }
}
</script>

<style scoped>
</style>
