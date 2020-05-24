<template>
  <v-container>
    <v-row>
      <v-col cols="12" class="headline">
        Number Squares
      </v-col>
      <v-col cols="12">
        Below table contains natural numbers and their squares.
      </v-col>
      <v-col cols="9" sm="5" md="3">
        <v-data-table :headers="headersSquare" :items="data" :items-per-page="-1" :mobile-breakpoint="null" hide-default-footer class="elevation-1" />
      </v-col>
      <v-col cols="12" class="headline">
        Number Cubes
      </v-col>
      <v-col cols="12">
        Below table contains natural numbers and their cubes.
      </v-col>
      <v-col cols="9" sm="5" md="3">
        <v-data-table :headers="headersCube" :items="data" :items-per-page="-1" :mobile-breakpoint="null" hide-default-footer class="elevation-1" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  computed: {
    headersSquare () {
      return [
        { text: 'n', align: 'right', class: 'title sticky-header grey lighten-3', sortable: false, value: 'n' },
        { text: 'n²', align: 'right', class: 'title sticky-header grey lighten-3', sortable: false, value: 'n2' }
      ]
    },

    headersCube () {
      return [
        { text: 'n', align: 'right', class: 'title sticky-header grey lighten-3', sortable: false, value: 'n' },
        { text: 'n³', align: 'right', class: 'title sticky-header grey lighten-3', sortable: false, value: 'n3' }
      ]
    },

    data () {
      return Array.from(Array(50).keys())
        .map(n => n + 1)
        .map(n => ({ n, n2: n * n, n3: n * n * n }))
    }
  }
}
</script>

<style scoped>
.v-data-table /deep/ .sticky-header {
  position: sticky;
  top: var(--mainBarHeight);
}

.v-data-table /deep/ .v-data-table__wrapper {
  overflow: unset;
}
</style>
