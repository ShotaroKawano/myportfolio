<template>
  <div class="main">
    <!-- mv -->
    <section id="mv">
      <h1 class="mv-msg"><span class="name">Shotaro Kawano</span><br>- works introduction -</h1>
    </section>
    <!-- products -->
    <section id="products">
      <v-container>
        <h2 class="section-title">Products</h2>
        <v-row>
          <v-col
            v-for="product in products"
            :key="product.title"
            cols="12" sm="6" md="4" lg="4"
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
    <!-- projects -->
    <section id="projects">
      <v-container>
        <h2 class="section-title">Projects</h2>
        <v-row>
          <v-col
            v-for="project in projects"
            :key="project.title"
            cols="12" sm="6" md="4" lg="4"
          >
          <Project
            :title="project.title"
            :period="project.period"
            :overview="project.overview"
            :thumnail="project.thumnail"
          />
          </v-col>
        </v-row>
      </v-container>
    </section>
    <!-- skills -->
    <section id="skills">
      <h2 class="section-title">Skills</h2>
      <div class="wrapper">
        <h3>- 概要</h3>
        <p>ITコンサルタントとして、SI・業務のRPA化を経験しました。ジーズアカデミー在籍時にVue.jsとdjnagoでサービスを開発しました。起業家のアイデアを実現できるようフルスタックな能力をつけていきたいと考えています。</p>
        <h3>- 言語</h3>
        <p>Python | JavaScript | PHP | Java(少し)</p>
        <h3>- フレームワーク</h3>
        <p>django | Vue.js | Laravel</p>
        <h3>- 受賞歴</h3>
        <p>G's ACADEMY TOKYO Hackathon 準優勝</p>
        <p>G's ACADEMY TOKYO- FUKUOKA 合同Hackathon 3位</p>
        <p>G's ACADEMY TOKYO Hackathon(チーム開発) 準優勝</p>
        <a href="https://gsacademy.jp/reading/2020/11/0050/" target="blank">G's ACADEMY TOKYO GLOBAL GEEK AUDITION 準優勝</a>
      </div>
    </section>
    <!-- about-me -->
    <section id="about-me">
      <h2 class="section-title">About me</h2>
      <div class="frame">
        <div class="icon"></div>
        <div class="introduction">
          <div class="intro-name">
            <p>川野翔太郎  Shotaro Kawano</p>
          </div>
          <div class="history">
            <p>埼玉出身 1994年生まれ</p>
            <p>Accenture卒</p>
            <p>立教大学理学部数学科主席卒業</p>
          </div>
          <div class="career">
            <p>大学卒業後、2017年にアクセンチュア入社</p>
            <p>システム開発・コンサルティング業務を経験し、退職</p>
            <p>ジーズアカデミー lab9期</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Product from '../components/Product'
import Project from '../components/Project'

export default {
  components: {
    Product,
    Project
  },
  data () {
    return {
      products: [
        {
          title: 'Sinapse',
          subtitle: '検索から課題解決までの情報を体系的につなげるサービス',
          technology: 'Vue.js/d3.js/django/ \ndjango REST framework',
          overview: '情報同士のつながりを表現するため、フローチャート×ブックマークのUIを採用 \n\nURL:https://sinapse-production.netlify.app/ \n\nloginID:test@test.com \nloginPass:test',
          videoId: '490669346'
        },
        {
          title: 'BOPS',
          subtitle: 'スーパーでの買物時間を1分に',
          technology: 'Laravel/Docker/EC2',
          overview: 'Buy Online Pick-up in Storeの略 \nスマホで事前注文しスーパーではピックアップするだけの想定で開発 \nwithコロナ時代の非接触での買い物、または子育て世帯の時短での買い物を実現するアプリ',
          videoId: '488214794'
        },
        {
          title: 'イベンタラクティブ',
          subtitle: 'イベントをインタラクティブに',
          technology: 'JavaScript/Firebase/Semantic UI',
          overview: 'イベントや授業で参加者にチャットの質問が埋もれてしまわないよう、質問だけ抽出することができる \nまたスピーカーの声は自動で文字起こしされ、アンケート機能で参加の声を集め、リアルタイムでグラフ化可能 \n\nURL:https://shotaro009.sakura.ne.jp/Eventeractive/',
          videoId: '488269804'
        },
        {
          title: 'XENO',
          subtitle: 'おうちでも一人でもXENO',
          technology: 'JavaScript',
          overview: '中田敦彦さんが開発したカードゲームXENOをコンピューター対戦で再現 \n\nURL:https://shotaro009.sakura.ne.jp/xeno/',
          videoId: '488262888'
        }
      ],
      projects: [
        {
          title: "G'S ACADEMY TOKYO",
          period: '2020年4月~2020年10月',
          overview: "プロダクトデモ、アントレプレナーシップについて学習 \nG's ACADEMY TOKYO Hackathon 準優勝 \nG's ACADEMY TOKYO-FUKUOKA 合同Hackathon 3位 \nG's ACADEMY TOKYO Hackathon(チーム開発) 準優勝",
          thumnail: 'gs-tokyo.png'
        },
        {
          title: 'M&A アドバイザリー企業コーポレートサイト作成',
          period: '2020年3月',
          overview: 'WordPressにてコーポレイトサイト作成 \n多言語化対応',
          thumnail: 'icp-capital-investment.png'
        },
        {
          title: '製造業企業在庫管理システム刷新',
          period: '2019年1月~2019年9月',
          overview: '製造業企業の倉庫・店舗の在庫管理システムの刷新プロジェクトにてアプリ領域を開発 \nシステム内のユーザ権限の要件定義と実装を担当 \n主に旧システムをリバースエンジニアリングして開発',
          thumnail: 'warehouse.jpg'
        },
        {
          title: 'メディア企業・製造業企業業務RPA化',
          period: '2018年6月~2019年1月',
          overview: '働き方改革の一環として業務RPA化を実施 \nヒアリング・業務プロセス分析・簡易なBPR・要件定義・設計・開発を担当 \n500h/年の業務時間削減に成功。',
          thumnail: 'rpa.jpg'
        },
        {
          title: '官公庁向け大規模システムのアーキテクチャ構築',
          period: '2017年9月~2018年5月',
          overview: 'IF領域のアーキテクチャの詳細設計・開発・単体・結合テスト・後続開発フェーズ向けドキュメント作成 \nオフショア開発のため英語にて業務遂行',
          thumnail: 'government-office.jpg'
        }
      ]
    }
  },
  mounted () {
    console.log(this.$vuetify.breakpoint)
  }
}
</script>

<style lang="scss" scoped>
.main {
  background-color: #eee;
}

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
  margin: 60px 0 30px 0;
}

#skills {
  /* 移動位置の調整 */
  padding-top: 30px;
}

.wrapper {
  width: 70%;
  margin: 0 auto;

  @media all and (max-width: 600px) {
    width: 90%;
  }
}

#about-me {
  padding-bottom: 50px;
}

.frame {
  width: 70%;
  margin: 0 auto;
  display: flex;

  @media all and (max-width: 600px) {
    display: block;
    width: 100%;
  }
}

.icon {
  width: 50%;
  height: 400px;
  background-image: url(~@/assets/profile.jpg);
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
  border-radius: 20px;

  @media all and (max-width: 600px) {
    width: 90%;
    margin: 0 auto;
  }
}

.introduction {
  width: 50%;
  padding: 24px;

  @media all and (max-width: 600px) {
    width: 90%;
    margin: 0 auto;
    padding: 16px;
  }
}

.intro-name {
  font-size: 1.6rem;
  margin-bottom: 40px;
}

.history {
  line-height: 1;
  margin-bottom: 40px;
}

.career {
  line-height: 1;
}
</style>
