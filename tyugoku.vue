<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" v-model="checkedNames" value="赤穂線">赤穂線
<input type="checkbox" v-model="checkedNames" value="姫新線">姫新線
<input type="checkbox" v-model="checkedNames" value="宇野線">宇野線
<input type="checkbox" v-model="checkedNames" value="津山線">津山線
<input type="checkbox" v-model="checkedNames" value="因美線">因美線
<input type="checkbox" v-model="checkedNames" value="吉備線">吉備線
<input type="checkbox" v-model="checkedNames" value="伯備線">伯備線
<input type="checkbox" v-model="checkedNames" value="境線">境線
<input type="checkbox" v-model="checkedNames" value="芸備線">芸備線
<input type="checkbox" v-model="checkedNames" value="福塩線">福塩線
<input type="checkbox" v-model="checkedNames" value="木次線">木次線
<input type="checkbox" v-model="checkedNames" value="三江線">三江線
<input type="checkbox" v-model="checkedNames" value="呉線">呉線
<input type="checkbox" v-model="checkedNames" value="可部線">可部線
<input type="checkbox" v-model="checkedNames" value="宇部線">宇部線
<input type="checkbox" v-model="checkedNames" value="山口線">山口線
<input type="checkbox" v-model="checkedNames" value="美祢線">美祢線
<input type="checkbox" v-model="checkedNames" value="山陽本線">山陽本線
<input type="checkbox" v-model="checkedNames" value="岩徳線">岩徳線
<input type="checkbox" v-model="checkedNames" value="小野田線">小野田線
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
    name: 'tyugoku',
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
        area:"中国",
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
