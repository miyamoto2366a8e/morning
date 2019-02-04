<template>
  <div class="hello animated fadeIn">
<h2>利用する鉄道を選択してください</h2>
<input type="checkbox" value="山手線" v-model="checkedNames">山手線
<input type="checkbox" value="湘南新宿ライン" v-model="checkedNames">湘南新宿ライン
<input type="checkbox" v-model="checkedNames" value="東海道線">東海道線
<input type="checkbox" v-model="checkedNames" value="横須賀線">横須賀線
<input type="checkbox" v-model="checkedNames" value="横浜線">横浜線
<input type="checkbox" v-model="checkedNames" value="相模線">相模線
<input type="checkbox" v-model="checkedNames" value="南武線">南武線
<input type="checkbox" v-model="checkedNames" value="中央線快速電車">中央線快速電車
<input type="checkbox" v-model="checkedNames" value="中央･総武各駅停車">中央･総武各駅停車
<input type="checkbox" v-model="checkedNames" value="総武快速線">総武快速線
<input type="checkbox" v-model="checkedNames" value="中央本線">中央本線
<input type="checkbox" v-model="checkedNames" value="総武本線">総武本線
<input type="checkbox" v-model="checkedNames" value="青梅線">青梅線
<input type="checkbox" v-model="checkedNames" value="五日市線">五日市線
<input type="checkbox" v-model="checkedNames" value="宇都宮線">宇都宮線
<input type="checkbox" v-model="checkedNames" value="高崎線">高崎線
<input type="checkbox" v-model="checkedNames" value="八高線">八高線
<input type="checkbox" v-model="checkedNames" value="日光線">日光線
<input type="checkbox" v-model="checkedNames" value="常磐線">常磐線
<input type="checkbox" v-model="checkedNames" value="常磐線快速電車">常磐線快速電車
<input type="checkbox" v-model="checkedNames" value="常磐線各駅停車">常磐線各駅停車
<input type="checkbox" v-model="checkedNames" value="内房線">内房線
<input type="checkbox" v-model="checkedNames" value="外房線">外房線
<input type="checkbox" v-model="checkedNames" value="成田線">成田線
<input type="checkbox" v-model="checkedNames" value="京葉線">京葉線
<input type="checkbox" v-model="checkedNames" value="武蔵野線">武蔵野線
<input type="checkbox" v-model="checkedNames" value="東金線">東金線
<input type="checkbox" v-model="checkedNames" value="久留里線">久留里線
<input type="checkbox" v-model="checkedNames" value="吾妻線">吾妻線
<input type="checkbox" v-model="checkedNames" value="水郡線">水郡線
<input type="checkbox" v-model="checkedNames" value="水戸線">水戸線
<input type="checkbox" v-model="checkedNames" value="両毛線">両毛線
<input type="checkbox" v-model="checkedNames" value="京浜東北線">京浜東北線
<input type="checkbox" v-model="checkedNames" value="西武線">西武線
<input type="checkbox" v-model="checkedNames" value="東武線">東武線
<input type="checkbox" v-model="checkedNames" value="銀座線">銀座線
<input type="checkbox" v-model="checkedNames" value="丸ノ内線">丸ノ内線
<input type="checkbox" v-model="checkedNames" value="日比谷線">日比谷線
<input type="checkbox" v-model="checkedNames" value="東西線">東西線
<input type="checkbox" v-model="checkedNames" value="千代田線">千代田線
<input type="checkbox" v-model="checkedNames" value="有楽町線">有楽町線
<input type="checkbox" v-model="checkedNames" value="半蔵門線">半蔵門線
<input type="checkbox" v-model="checkedNames" value="南北線">南北線
<input type="checkbox" v-model="checkedNames" value="副都心線">副都心線
<input type="checkbox" v-model="checkedNames" value="京成線">京成線
<input type="checkbox" v-model="checkedNames" value="京王電鉄線">京王電鉄線
<input type="checkbox" v-model="checkedNames" value="浅草線">浅草線
<input type="checkbox" v-model="checkedNames" value="三田線">三田線
<input type="checkbox" v-model="checkedNames" value="新宿線">新宿線
<input type="checkbox" v-model="checkedNames" value="大江戸線">大江戸線
<input type="checkbox" v-model="checkedNames" value="小田急線">小田急線
<input type="checkbox" v-model="checkedNames" value="東京モノレール">東京モノレール
<input type="checkbox" v-model="checkedNames" value="りんかい線">りんかい線
<input type="checkbox" v-model="checkedNames" value="京急線">京急線
<input type="checkbox" v-model="checkedNames" value="日暮里･舎人ライナー">日暮里･舎人ライナー
<input type="checkbox" v-model="checkedNames" value="相鉄線">相鉄線
<input type="checkbox" v-model="checkedNames" value="東急線">東急線
<input type="checkbox" v-model="checkedNames" value="横浜市営地下鉄">横浜市営地下鉄
<input type="checkbox" v-model="checkedNames" value="ゆりかもめ">ゆりかもめ
<input type="checkbox" v-model="checkedNames" value="埼京線">埼京線
<input type="checkbox" v-model="checkedNames" value="川越線">川越線
<input type="checkbox" v-model="checkedNames" value="千葉モノレール">千葉モノレール
<input type="checkbox" v-model="checkedNames" value="多摩モノレール">多摩モノレール
<input type="checkbox" v-model="checkedNames" value="山陽電鉄線">山陽電鉄線
<input type="checkbox" v-model="checkedNames" value="つくばエクスプレス線">つくばエクスプレス線
<input type="checkbox" v-model="checkedNames" value="新京成線">新京成線
<input type="checkbox" v-model="checkedNames" value="伊東線">伊東線
<input type="checkbox" v-model="checkedNames" value="高徳線">高徳線
<input type="checkbox" v-model="checkedNames" value="烏山線">烏山線
<input type="checkbox" v-model="checkedNames" value="鶴見線">鶴見線
<input type="checkbox" v-model="checkedNames" value="鹿島線">鹿島線
<br><br>
(電車利用地区：関東。利用路線：{{this.checkedNames}})
<p><button @click="hozon">上記設定をサーバーに保存</button></p>
<p><button @click="back">保存せず１つ前の画面へ戻る</button></p>
{{this.checkedNames}}
  </div>
</template>

<script>
import {db} from '../plugins/firebase';
import firebase from 'firebase'
import { EnhancedCheck } from 'vue-enhanced-check'
  export default {
    components: { EnhancedCheck },
    name: 'kanto',
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
        area:"関東",
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
