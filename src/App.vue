<template>
  <v-app>
    <v-container>
      <v-main>
        <v-layout justify-center>
          <v-flex shrink>
            <ScrollContainer :max-height="600">
              <template v-slot:big-card>
                <FullSizeCard :opacity="1" style="position: absolute; z-index: 10" />
              </template>
              <template v-slot:small-card>
                <ShrinkSizeCard style="position: absolute; z-index: 1" />
              </template>
              <v-container style="height: 10000px"></v-container>
            </ScrollContainer>
          </v-flex>
        </v-layout>
      </v-main>
    </v-container>
  </v-app>
</template>

<script>
import ScrollContainer from './components/Example'
import FullSizeCard from '@/components/FullSizeCard.vue'
import ShrinkSizeCard from '@/components/ShrinkSizeCard.vue'

export default {
  name: 'App',

  components: {
    ScrollContainer,
    FullSizeCard,
    ShrinkSizeCard
  },

  data: () => ({
    //
  })
}
</script>
