<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" v-model="checkedNames" value="東北本線">東北本線
<input type="checkbox" v-model="checkedNames" value="仙山線">仙山線
<input type="checkbox" v-model="checkedNames" value="仙石線">仙石線
<input type="checkbox" v-model="checkedNames" value="磐越東線">磐越東線
<input type="checkbox" v-model="checkedNames" value="磐越西線">磐越西線
<input type="checkbox" v-model="checkedNames" value="石巻線">石巻線
<input type="checkbox" v-model="checkedNames" value="気仙沼線">気仙沼線
<input type="checkbox" v-model="checkedNames" value="釜石線">釜石線
<input type="checkbox" v-model="checkedNames" value="八戸線">八戸線
<input type="checkbox" v-model="checkedNames" value="大湊線">大湊線
<input type="checkbox" v-model="checkedNames" value="山形線">山形線
<input type="checkbox" v-model="checkedNames" value="奥羽本線">奥羽本線
<input type="checkbox" v-model="checkedNames" value="米坂線">米坂線
<input type="checkbox" v-model="checkedNames" value="左沢線">左沢線
<input type="checkbox" v-model="checkedNames" value="陸羽東線">陸羽東線
<input type="checkbox" v-model="checkedNames" value="陸羽西線">陸羽西線
<input type="checkbox" v-model="checkedNames" value="北上線">北上線
<input type="checkbox" v-model="checkedNames" value="田沢湖線">田沢湖線
<input type="checkbox" v-model="checkedNames" value="花輪線">花輪線
<input type="checkbox" v-model="checkedNames" value="男鹿線">男鹿線
<input type="checkbox" v-model="checkedNames" value="五能線">五能線
<input type="checkbox" v-model="checkedNames" value="津軽線">津軽線
<input type="checkbox" v-model="checkedNames" value="羽越本線">羽越本線
<input type="checkbox" v-model="checkedNames" value="白新線">白新線
<input type="checkbox" v-model="checkedNames" value="青い森鉄道線">青い森鉄道線
<input type="checkbox" v-model="checkedNames" value="仙台市営地下鉄">仙台市営地下鉄
<input type="checkbox" v-model="checkedNames" value="大船渡線">大船渡線
<input type="checkbox" v-model="checkedNames" value="只見線">只見線
<input type="checkbox" v-model="checkedNames" value="山田線">山田線
<input type="checkbox" v-model="checkedNames" value="ほくほく線">ほくほく線
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
    name: 'touhoku',
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
        area:"東北",
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
