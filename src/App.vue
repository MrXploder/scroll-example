<template>
  <v-app>
    <v-container>
      <v-main>
        <v-layout justify-center>
          <v-flex shrink>
            <Example />
          </v-flex>
        </v-layout>
      </v-main>
    </v-container>
  </v-app>
</template>

<script>
import Example from './components/Example'

export default {
  name: 'App',

  components: {
    Example
  },

  data: () => ({
    //
  })
}
</script>
