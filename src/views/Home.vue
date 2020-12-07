<template>
  <div>
    <section id="mv">
      <h1><span class="name">Shotaro Kawano</span><br>- works introduction -</h1>
    </section>
    <section id="products">
      <v-container>
        <v-row>
          <v-col
            v-for="product in products"
            :key="product.title"
            cols="12" sm="6" md="4" lg="3"
          >
          <Product
            :title="product.title"
            :videoId="product.videoId"
            :overview="product.overview"
            :technology="product.technology"
          />
          </v-col>
          <!-- <v-col>
          <Product
            title="タイトル"
            video="ビデオ"
            overview="オーバービュー"
            technology="テクノロジー"
          />
          </v-col> -->
          <!-- <v-col cols="12" sm="6" md="4" lg="3">
          <Product />
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
          <Product />
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
          <Product />
          </v-col> -->
        </v-row>
      </v-container>
    </section>
    <section id="projects"></section>
    <section id="skills"></section>
    <section id="about-me"></section>
  </div>
</template>

<script>
import Product from '../components/Product'

export default {
  components: {
    Product
  },
  data () {
    return {
      products: [
        {
          title: 'BOPS',
          videoId: '488214794',
          overview: 'オーバービュー',
          technology: 'Laravel/Docker/EC2'
        },
        {
          title: 'Sinapse',
          videoId: '488219528',
          overview: 'オーバービュー',
          technology: 'Vue.js/d3.js/django/django REST framework'
        },
        {
          title: 'XENO',
          videoId: 'ビデオ',
          overview: 'オーバービュー',
          technology: 'テクノロジー'
        },
        {
          title: 'イベンタラクティブ',
          videoId: 'ビデオ',
          overview: 'オーバービュー',
          technology: 'テクノロジー'
        }
      ]
    }
  },
  mounted () {
    console.log(this.$vuetify.breakpoint)
  }
}
</script>

<style scoped>
#mv {
  width: 100%;
  height: 200px;
  background-image: url(~@/assets/Andromeda.jpg);
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
}

#mv h1 {
  color: #fff;
  text-align: center;
  padding-top: 50px;
}

#mv h1 .name {
  font-size: 2rem;
}
</style>
