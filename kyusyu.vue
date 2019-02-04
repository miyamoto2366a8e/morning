<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" v-model="checkedNames" value="鹿児島本線">鹿児島本線
<input type="checkbox" v-model="checkedNames" value="日豊本線">日豊本線
<input type="checkbox" v-model="checkedNames" value="日田彦山線">日田彦山線
<input type="checkbox" v-model="checkedNames" value="筑肥線">筑肥線
<input type="checkbox" v-model="checkedNames" value="長崎本線">長崎本線
<input type="checkbox" v-model="checkedNames" value="佐世保線">佐世保線
<input type="checkbox" v-model="checkedNames" value="大村線">大村線
<input type="checkbox" v-model="checkedNames" value="肥薩線">肥薩線
<input type="checkbox" v-model="checkedNames" value="吉都線">吉都線
<input type="checkbox" v-model="checkedNames" value="日南線">日南線
<input type="checkbox" v-model="checkedNames" value="指宿枕崎線">指宿枕崎線
<input type="checkbox" v-model="checkedNames" value="西鉄線">西鉄線
<input type="checkbox" v-model="checkedNames" value="福岡市営地下鉄">福岡市営地下鉄
<input type="checkbox" v-model="checkedNames" value="宮崎空港線">宮崎空港線
<input type="checkbox" v-model="checkedNames" value="久大本線">久大本線
<input type="checkbox" v-model="checkedNames" value="唐津線">唐津線
<input type="checkbox" v-model="checkedNames" value="後藤寺線">後藤寺線
<input type="checkbox" v-model="checkedNames" value="香椎線">香椎線
<input type="checkbox" v-model="checkedNames" value="三角線">三角線
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
    name: 'kyusyu',
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
        area:"九州",
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
