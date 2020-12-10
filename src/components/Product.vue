<template>
  <v-card
    class="mx-auto"
    max-width="344"
  >
      <!-- src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" -->
    <!-- <v-img
      src="https://www.youtube.com/watch?v=3JMZ5HWdzmU&feature=youtu.be"
      height="200px"
    ></v-img> -->
      <!-- src="https://player.vimeo.com/video/488214794" -->
    <iframe
      :src="vimeoUrl"
      width="100%"
      frameborder="0"
      allow="autoplay; fullscreen"
      allowfullscreen>
    </iframe>

    <v-card-title>
      {{ title }}
    </v-card-title>

    <v-card-subtitle
      class="subtitle"
    >
      〜{{ subtitle }}〜
    </v-card-subtitle>

    <v-card-text
      class="technology"
      style="white-space: pre-wrap;"
    >
      {{ technology }}
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="orange lighten-2"
        text
        @click="show = !show"
      >
        more
        <!-- site -->
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>

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
    subtitle: {
      type: String,
      default: ''
    },
    videoId: {
      type: String,
      default: ''
    },
    overview: {
      type: String,
      default: ''
    },
    technology: {
      type: String,
      default: ''
    }
  },
  data: () => ({
    show: false,
    vimeoUrl: ''
  }),
  created: function () {
    this.vimeoUrl = 'https://player.vimeo.com/video/' + this.videoId
  }
}
</script>

<style scoped>
.subtitle {
  line-height: 1rem;
  height: 2rem;
  margin: 10px 0;
}

.technology {
  line-height: 1rem;
  height: 2rem;
}
</style>
