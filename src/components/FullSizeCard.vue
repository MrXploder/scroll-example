<template>
  <div class="fill-space orange py-2 px-8 overflow-hidden" :style="{ opacity }">
    <v-layout align-baseline justify-space-between>
      <v-flex shrink>
        <v-layout align-baseline>
          <v-flex shrink>
            <v-btn icon x-small color="white">
              <v-icon>mdi-arrow-left</v-icon>
            </v-btn>
          </v-flex>
          <v-flex shrink>
            <p class="white--text ml-2">Volver a empleos</p>
          </v-flex>
        </v-layout>
      </v-flex>
      <v-flex shrink>
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

    <v-layout class="mt-12" align-center justify-space-between>
      <v-flex shrink>
        <v-layout>
          <v-flex shrink class="mr-4">
            <v-layout column class="ma-0">
              <v-flex shrink>
                <v-img src="https://via.placeholder.com/78" :height="78" :width="78" style="border-radius: 4px"></v-img>
              </v-flex>
              <v-flex shrink>
                <v-btn x-small>Siguiendo</v-btn>
              </v-flex>
            </v-layout>
          </v-flex>

          <v-flex shrink>
            <v-layout column class="ma-0">
              <h3 class="white--text font-weight-bold mb-2">Nombre del Empleo</h3>
              <h6 class="white--text">Región y comuna del empleo</h6>
              <h6 class="white--text">Área del empleo</h6>
              <h6 class="white--text">Sueldo del empleo</h6>
            </v-layout>
          </v-flex>
        </v-layout>
      </v-flex>
      <v-flex shrink>
        <v-layout column class="ma-0">
          <v-flex shrink class="mb-3">
            <v-btn>Postular</v-btn>
          </v-flex>
          <v-layout align-baseline justify-end>
            <v-flex shrink class="mr-2">
              <p class="white--text">Compartir</p>
            </v-flex>
            <v-flex shrink>
              <v-btn fab x-small color="blue" dark depressed>
                <v-icon>mdi-share-variant-outline</v-icon>
              </v-btn>
            </v-flex>
          </v-layout>
        </v-layout>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  props: {
    opacity: { type: Number, default: 1 }
  }
}
</script>

<style></style>
