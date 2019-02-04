<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" v-model="checkedNames" value="大阪環状線">大阪環状線
<input type="checkbox" v-model="checkedNames" value="ＪＲゆめ咲線">ＪＲゆめ咲線
<input type="checkbox" v-model="checkedNames" value="ＪＲ宝塚線">ＪＲ宝塚線
<input type="checkbox" v-model="checkedNames" value="琵琶湖線">琵琶湖線
<input type="checkbox" v-model="checkedNames" value="ＪＲ京都線">ＪＲ京都線
<input type="checkbox" v-model="checkedNames" value="湖西線">湖西線
<input type="checkbox" v-model="checkedNames" value="草津線">草津線
<input type="checkbox" v-model="checkedNames" value="嵯峨野線">嵯峨野線
<input type="checkbox" v-model="checkedNames" value="学研都市線">学研都市線
<input type="checkbox" v-model="checkedNames" value="ＪＲ東西線">ＪＲ東西線
<input type="checkbox" v-model="checkedNames" value="ＪＲ神戸線">ＪＲ神戸線
<input type="checkbox" v-model="checkedNames" value="阪和線">阪和線
<input type="checkbox" v-model="checkedNames" value="大和路線">大和路線
<input type="checkbox" v-model="checkedNames" value="奈良線">奈良線
<input type="checkbox" v-model="checkedNames" value="和歌山線">和歌山線
<input type="checkbox" v-model="checkedNames" value="関西空港線">関西空港線
<input type="checkbox" v-model="checkedNames" value="きのくに線">きのくに線
<input type="checkbox" v-model="checkedNames" value="加古川線">加古川線
<input type="checkbox" v-model="checkedNames" value="播但線">播但線
<input type="checkbox" v-model="checkedNames" value="舞鶴線">舞鶴線
<input type="checkbox" v-model="checkedNames" value="小浜線">小浜線
<input type="checkbox" v-model="checkedNames" value="福知山線">福知山線
<input type="checkbox" v-model="checkedNames" value="山陰本線">山陰本線
<input type="checkbox" v-model="checkedNames" value="おおさか東線">おおさか東線
<input type="checkbox" v-model="checkedNames" value="大阪市営地下鉄">大阪市営地下鉄
<input type="checkbox" v-model="checkedNames" value="京阪線">京阪線
<input type="checkbox" v-model="checkedNames" value="阪神線">阪神線
<input type="checkbox" v-model="checkedNames" value="神戸電鉄線">神戸電鉄線
<input type="checkbox" v-model="checkedNames" value="大阪モノレール">大阪モノレール
<input type="checkbox" v-model="checkedNames" value="万葉まほろば線">万葉まほろば線
<input type="checkbox" v-model="checkedNames" value="阪急線">阪急線
<input type="checkbox" v-model="checkedNames" value="南海線">南海線
<input type="checkbox" v-model="checkedNames" value="近鉄線">近鉄線
<input type="checkbox" v-model="checkedNames" value="豊肥本線">豊肥本線
<input type="checkbox" v-model="checkedNames" value="能勢電鉄線">能勢電鉄線
<br><br>
<h2>利用路線：{{this.checkedNames}}</h2>
<p><button @click="hozon">上記設定をサーバーに保存</button></p>
<p><button @click="back">保存せず１つ前の画面へ戻る</button></p>
  </div>
</template>

<script>
import {db} from '../plugins/firebase';
import firebase from 'firebase'
import { EnhancedCheck } from 'vue-enhanced-check'
  export default {
    components: { EnhancedCheck },
    name: 'kinki',
    data() {
      return {
        myset: "",
        checkedNames: []
      }
    },
  created() {
    if(this.$store.state.signflag == 0){
  alert("ログインしていません")
  this.$router.push('/sign')
}
  },
  methods: {
    hozon() {
        db.collection('user').doc(this.$store.state.uid).collection('rosen').doc('rosen').set({
        area:"近畿",
         rosen: this.checkedNames
          })
        alert("保存しました")
        this.$router.push('/conf')
    },
     back() {
       this.$router.push('/conf')
     }
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1,
  h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
    .hello{
    text-align:center;
  }
</style>
