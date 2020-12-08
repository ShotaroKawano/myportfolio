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
          title: 'Sinapse',
          videoId: '488219528',
          overview: 'ブックマークのシェアと検索ができるサービス。情報同士のつながりを表現するため、フローチャート×ブックマークのUIを採用している。URL:https://sinapse-production.netlify.app/ loginID:test@test.com loginPass:test',
          technology: 'Vue.js/d3.js/django/django REST framework'
        },
        {
          title: 'BOPS',
          videoId: '488214794',
          overview: '〜スーパーでの買物時間を1分に〜 Buy Online Pick-up in Storeの略。 スマホで事前注文し、スーパーではピックアップするだけ。withコロナ時代の非接触での買い物、または子育て世帯の時短での買い物を実現するアプリ。',
          technology: 'Laravel/Docker/EC2'
        },
        {
          title: 'イベンタラクティブ',
          videoId: '488269804',
          overview: '〜イベントをインタラクティブに〜 イベントや授業で参加者にチャットの質問が埋もれてしまわないよう、質問だけ抽出することができる。またスピーカーの声は自動で文字起こしされ、アンケート機能で参加の声を集め、リアルタイムでグラフ化することができる。URL:https://shotaro009.sakura.ne.jp/Eventeractive/',
          technology: 'JavaScript/Firebase/Semantic UI'
        },
        {
          title: 'XENO',
          videoId: '488262888',
          overview: '〜おうちでも一人でもXENO〜 中田敦彦さんが開発したカードゲームXENOをコンピューター対戦で再現。URL:https://shotaro009.sakura.ne.jp/xeno/',
          technology: 'JavaScript'
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
