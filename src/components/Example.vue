<template>
  <v-card class="overflow-hidden" width="600px">
    <v-app-bar
      hide-on-scroll
      :scroll-threshold="toolbarConfig.hideOnScrollThreshold"
      absolute
      :scroll-target="`#${scrollTargetId}`"
      flat
      :style="{ 'max-height': toolbarConfig.maxHeight }"
      style="background-color: transparent"
    >
      <v-app-bar
        shrink-on-scroll
        :scroll-target="`#${scrollTargetId}`"
        :height="toolbarConfig.maxHeight"
        :min-height="toolbarConfig.minHeight"
        prominent
        absolute
        class="inner-toolbar"
        style="background-color: transparent"
      >
        <div style="position: relative" class="fill-space">
          <FullSizeCard :opacity="opacity" style="position: absolute; z-index: 10" />
          <ShrinkSizeCard style="position: absolute; z-index: 1" />
        </div>
      </v-app-bar>
    </v-app-bar>
    <!-- Para que funcione el contenido debe ser mas alto que el contenedor, para que haya "overflow" y funcione los scroll event -->
    <v-sheet class="overflow-y-auto" max-height="600" :id="scrollTargetId">
      <v-container style="height: 10000px"></v-container>
    </v-sheet>
  </v-card>
</template>

<script>
import FullSizeCard from '@/components/FullSizeCard.vue'
import ShrinkSizeCard from '@/components/ShrinkSizeCard.vue'

export default {
  name: 'Example',

  components: {
    FullSizeCard,
    ShrinkSizeCard
  },

  data: () => ({
    opacity: 1,
    scrollTargetId: 'scrollable-div',
    toolbarConfig: {
      minHeight: '64px',
      maxHeight: '250px',
      hideOnScrollThreshold: 1000,
      scrollTopLimit: 124
    }
  }),

  computed: {
    scrollElement() {
      return document.getElementById(this.scrollTargetId)
    }
  },

  methods: {
    onScrollChange() {
      const scrollTop = this.scrollElement.scrollTop
      const scrollHeight = this.scrollElement.scrollHeight
      console.log({ scrollTop, scrollHeight })
      if (scrollTop > this.toolbarConfig.scrollTopLimit) {
        this.opacity = 0
      } else {
        this.opacity = 1 + (scrollTop * -1) / this.toolbarConfig.scrollTopLimit
      }
    }
  },

  mounted() {
    this.scrollElement.addEventListener('scroll', this.onScrollChange.bind(this))
  },

  beforeDestroy() {
    this.scrollElement.removeEventListener('scroll', this.onScrollChange.bind(this))
  }
}
</script>

<style lang="scss" scoped>
.inner-toolbar::v-deep {
  .v-toolbar__content {
    padding: 0;
    height: 100% !important;
  }
}
</style>
