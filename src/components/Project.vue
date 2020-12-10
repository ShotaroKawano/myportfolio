<template>
  <v-card
    class="mx-auto"
    max-width="344"
    height="400px"
  >
    <v-img
      :src="this.requireImg()"
      height="200px"
    ></v-img>

    <v-card-title>
      {{ title }}
    </v-card-title>

    <v-card-subtitle>
      {{ period }}
    </v-card-subtitle>

    <v-card-text
      class="overview"
      style="white-space: pre-wrap;"
    >
      {{ overview }}
    </v-card-text>

    <!-- <v-card-actions>
      <v-btn
        color="orange lighten-2"
        text
        @click="show = !show"
      >
        more
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions> -->

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text
          style="white-space: pre-wrap;"
        >
          {{ overview }}
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    period: {
      type: String,
      default: ''
    },
    overview: {
      type: String,
      default: ''
    },
    thumnail: {
      type: String,
      default: ''
    }
  },
  data: () => ({
    show: false,
    vimeoUrl: '',
    image_src: ''
  }),
  created: function () {
    this.vimeoUrl = 'https://player.vimeo.com/video/' + this.videoId
  },
  methods: {
    requireImg () {
      return require('@/assets/' + this.thumnail)
    }
  }
}
</script>

<style scoped>
.title {
  line-height: 1rem;
  height: 2rem;
}

.overview {
  line-height: 1rem;
  height: 2rem;
}
</style>
