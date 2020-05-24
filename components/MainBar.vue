<template>
  <v-app-bar ref="toolbar" v-mutate="onMutate" app prominent dark src="https://picsum.photos/1600/300?grayscale" shrink-on-scroll fade-img-on-scroll scroll-threshold="500">
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
      document.documentElement.style.setProperty('--toolbarHeight', height)
    }
  }
}
</script>

<style scoped>
</style>
