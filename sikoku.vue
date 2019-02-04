<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<input type="checkbox" name="riyu" value="瀬戸大橋線">瀬戸大橋線
<input type="checkbox" name="riyu" value="予讃線">予讃線
<input type="checkbox" name="riyu" value="土讃線">土讃線
<input type="checkbox" name="riyu" value="牟岐線">牟岐線
<input type="checkbox" name="riyu" value="徳島線">徳島線
<input type="checkbox" name="riyu" value="予土線">予土線
<input type="checkbox" name="riyu" value="鳴門線">鳴門線
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
    name: 'sikoku',
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
        area:"四国",
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
