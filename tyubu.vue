<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" v-model="checkedNames" value="名鉄線">名鉄線
<input type="checkbox" v-model="checkedNames" value="東海道本線">東海道本線
<input type="checkbox" v-model="checkedNames" value="御殿場線">御殿場線
<input type="checkbox" v-model="checkedNames" value="身延線">身延線
<input type="checkbox" v-model="checkedNames" value="飯田線">飯田線
<input type="checkbox" v-model="checkedNames" value="武豊線">武豊線
<input type="checkbox" v-model="checkedNames" value="太多線">太多線
<input type="checkbox" v-model="checkedNames" value="関西本線">関西本線
<input type="checkbox" v-model="checkedNames" value="紀勢本線">紀勢本線
<input type="checkbox" v-model="checkedNames" value="参宮線">参宮線
<input type="checkbox" v-model="checkedNames" value="名松線">名松線
<input type="checkbox" v-model="checkedNames" value="小海線">小海線
<input type="checkbox" v-model="checkedNames" value="篠ノ井線">篠ノ井線
<input type="checkbox" v-model="checkedNames" value="信越本線">信越本線
<input type="checkbox" v-model="checkedNames" value="飯山線">飯山線
<input type="checkbox" v-model="checkedNames" value="越後線">越後線
<input type="checkbox" v-model="checkedNames" value="弥彦線">弥彦線
<input type="checkbox" v-model="checkedNames" value="上越線">上越線
<input type="checkbox" v-model="checkedNames" value="北陸本線">北陸本線
<input type="checkbox" v-model="checkedNames" value="九頭竜線">九頭竜線
<input type="checkbox" v-model="checkedNames" value="七尾線">七尾線
<input type="checkbox" v-model="checkedNames" value="氷見線">氷見線
<input type="checkbox" v-model="checkedNames" value="城端線">城端線
<input type="checkbox" v-model="checkedNames" value="高山本線">高山本線
<input type="checkbox" v-model="checkedNames" value="大糸線">大糸線
<input type="checkbox" v-model="checkedNames" value="名古屋市営地下鉄">名古屋市営地下鉄
<input type="checkbox" v-model="checkedNames" value="しなの鉄道線">しなの鉄道線
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
    name: 'tyubu',
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
        area:"中部",
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
