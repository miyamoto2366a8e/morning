<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" v-model="checkedNames" value="日高本線">日高本線
<input type="checkbox" v-model="checkedNames" value="花咲線">花咲線
<input type="checkbox" v-model="checkedNames" value="津軽海峡線">津軽海峡線
<input type="checkbox" v-model="checkedNames" value="札沼線">札沼線
<input type="checkbox" v-model="checkedNames" value="函館本線">函館本線
<input type="checkbox" v-model="checkedNames" value="千歳線">千歳線
<input type="checkbox" v-model="checkedNames" value="学園都市線">学園都市線
<input type="checkbox" v-model="checkedNames" value="宗谷本線">宗谷本線
<input type="checkbox" v-model="checkedNames" value="石北本線">石北本線
<input type="checkbox" v-model="checkedNames" value="釧網本線">釧網本線
<input type="checkbox" v-model="checkedNames" value="留萌本線">留萌本線
<input type="checkbox" v-model="checkedNames" value="根室本線">根室本線
<input type="checkbox" v-model="checkedNames" value="富良野線">富良野線
<input type="checkbox" v-model="checkedNames" value="石勝線">石勝線
<input type="checkbox" v-model="checkedNames" value="室蘭本線">室蘭本線
<input type="checkbox" v-model="checkedNames" value="江差線">江差線

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
    name: 'hokkaido',
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
        area:"北海道",
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
