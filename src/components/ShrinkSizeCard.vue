<template>
  <v-layout align-baseline class="orange fill-space pa-4" style="opacity: 0.5">
    <v-flex shrink class="mr-4">
      <v-btn>Postular</v-btn>
    </v-flex>

    <v-flex shrink>
      <v-layout align-baseline>
        <v-flex shrink>
          <v-btn fab x-small color="blue" dark depressed class="mr-2">
            <v-icon>mdi-share-variant-outline</v-icon>
          </v-btn>
        </v-flex>
        <v-flex shrink>
          <p class="white--text">Compartir</p>
        </v-flex>
      </v-layout>
    </v-flex>

    <v-flex shrink class="ml-auto">
      <v-layout align-baseline>
        <v-flex shrink class="mr-2">
          <p class="white--text">Guardar</p>
        </v-flex>
        <v-flex>
          <v-btn icon color="white" small>
            <v-icon>mdi-heart-outline</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-flex>
  </v-layout>
</template>

<script>
export default {}
</script>

<style></style>
