<template>
  <div>
    <section id="mv">
      <h1 class="mv-msg"><span class="name">Shotaro Kawano</span><br>- works introduction -</h1>
    </section>
    <section id="products">
      <v-container>
        <h2 class="section-title">Products</h2>
        <v-row>
          <v-col
            v-for="product in products"
            :key="product.title"
            cols="12" sm="6" md="4" lg="3"
          >
          <Product
            :title="product.title"
            :subtitle="product.subtitle"
            :videoId="product.videoId"
            :overview="product.overview"
            :technology="product.technology"
          />
          </v-col>
        </v-row>
      </v-container>
    </section>
    <section id="projects"></section>
    <section id="skills">
    </section>
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
          subtitle: 'ブックマークのシェアと検索ができるサービス',
          videoId: '488219528',
          overview: '情報同士のつながりを表現するため、フローチャート×ブックマークのUIを採用 \n\nURL:https://sinapse-production.netlify.app/ \n\nloginID:test@test.com \nloginPass:test',
          technology: 'Vue.js/d3.js/django/ \ndjango REST framework'
        },
        {
          title: 'BOPS',
          subtitle: 'スーパーでの買物時間を1分に',
          videoId: '488214794',
          overview: 'Buy Online Pick-up in Storeの略 \nスマホで事前注文しスーパーではピックアップするだけの想定で開発 \nwithコロナ時代の非接触での買い物、または子育て世帯の時短での買い物を実現するアプリ',
          technology: 'Laravel/Docker/EC2'
        },
        {
          title: 'イベンタラクティブ',
          subtitle: 'イベントをインタラクティブに',
          videoId: '488269804',
          overview: 'イベントや授業で参加者にチャットの質問が埋もれてしまわないよう、質問だけ抽出することができる \nまたスピーカーの声は自動で文字起こしされ、アンケート機能で参加の声を集め、リアルタイムでグラフ化可能 \n\nURL:https://shotaro009.sakura.ne.jp/Eventeractive/',
          technology: 'JavaScript/Firebase/Semantic UI'
        },
        {
          title: 'XENO',
          subtitle: 'おうちでも一人でもXENO',
          videoId: '488262888',
          overview: '中田敦彦さんが開発したカードゲームXENOをコンピューター対戦で再現 \n\nURL:https://shotaro009.sakura.ne.jp/xeno/',
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

#mv .mv-msg {
  color: #fff;
  text-align: center;
  padding-top: 50px;
}

#mv .mv-msg .name {
  font-size: 2rem;
}

.section-title {
  font-size: 2rem;
  text-align: center;
  margin: 30px 0;
}

</style>
