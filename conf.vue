<template>
  <div class="hello animated fadeIn">
    <!-- 遅延情報を何分前にチェックしますか？<br>
    <input type="number" name="riyu" value="1"><br> -->
<h1>表示する秘書を選択してください</h1>
現在設定：{{this.hisyo_name}}<br>
<el-button type="primary" round　@click="hisyo = 0; hisyo_name = 'ハル(受付バージョン)';hisyo_hozon($event)">ハル(受付バージョン)</el-button>
<!-- <el-button type="primary" round　@click="hisyo = 2; hisyo_name = '名執　尽';hisyo_hozon($event)">名執　尽</el-button> -->
<el-button type="primary" round　@click="hisyo = 3; hisyo_name = 'わんころもち';hisyo_hozon($event)">わんころもち</el-button>
<br>※「Powered by Live2D」<br><br>
<h1>表示する情報を選択してください</h1>
<input type="checkbox" v-model='hyoji["tien"]'>遅延情報
<input type="checkbox" v-model='hyoji["weather"]'>天気予報
<input type="checkbox" v-model='hyoji["nikkei"]'>日経平均表示
<input type="checkbox" v-model='hyoji["yotei"]'>予定機能
<input type="checkbox" v-model='hyoji["otoku"]'>お得情報
<input type="checkbox" v-model='hyoji["news"]'>ニュース
<input type="checkbox" v-model='hyoji["fx"]'>為替
<p><el-button type="primary" round　@click="settei">設定を変更する</el-button></p><br>
<h1>天気予報</h1>
<h2>現在の設定：{{this.$store.state.weatherName}}</h2>
<p><el-button type="primary" round　@click="tenki">地域を選ぶ</el-button></p><br>
<h2>利用する鉄道を選択してください</h2>
現在選択中{{this.$store.state.rosen}}
<div class="tetudo">
    <img src="../assets/map2.png" width="100%">
<el-button type="primary" round　@click="hokkaido" class="hokkaido">北海道</el-button>
<el-button type="primary" round @click="touhoku" class="touhoku">東北</el-button>
<el-button type="primary" round @click="kanto" class="kanto">関東</el-button>
<el-button type="primary" round @click="tyubu" class="tyubu">中部</el-button>
<el-button type="primary" round @click="kinki" class="kinki">近畿</el-button>
<el-button type="primary" round @click="tyugoku" class="tyugoku">中国</el-button>
<el-button type="primary" round @click="sikoku" class="sikoku">四国</el-button>
<el-button type="primary" round @click="kyusyu" class="kyusyu">九州</el-button>
<el-button type="primary" round @click="etc" class="etc">etc</el-button>
</div>
  </div>
</template>

<script>
import {db} from '../plugins/firebase';
import firebase from 'firebase'
// import moment from 'moment';
  export default {
    name: 'conf',
    data() {
      return {
        weather:"",
        weatherName:"",
        tien:"",
        tien2:"",
        hisyo:"0",
        hisyo_name:"ハル(受付バージョン)",
        hyoji:{
            tien:true,
            weather:true,
            nikkei:true,
            yotei:true,
            otoku:true,
            news:true,
            fx:true
        }
      }
    },
  created() {
if(this.$store.state.signflag == 0){
  alert("ログインしていません")
  this.$router.push('/sign')
}
    db.collection('user').doc(this.$store.state.uid).collection('hisyo').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.data());
      var fuga = doc.data()
      this.hisyo = fuga["hisyo"]
      this.hisyo_name = fuga["hisyo_name"]
    });
});
  },
  methods: {
    tienflag(){
        if(this.tien == true){
        console.log("true")}else{console.log("false")}
    },
    tenki(){
        this.$router.push('/map')
    },
    hisyo_hozon(){
        console.log("hoge")
         db.collection('user').doc(this.$store.state.uid).collection('hisyo').doc('hoge').set({
         hisyo: this.hisyo,
         hisyo_name: this.hisyo_name
          });
    },
    settei(){
         db.collection('user').doc(this.$store.state.uid).collection('hyoji').doc('hoge').set({
         hyoji: this.hyoji
          });
            alert("設定を保存しました")
    },
    al(){
    this.$store.commit('setWeather', this.weather)
switch( this.weather ) {
    case "2112669":
        this.$store.commit('setWeatherName', "茨城")
        break;
    case "1850147":
        this.$store.commit('setWeatherName', "東京")
        break;
    case "1853904":
        this.$store.commit('setWeatherName', "大阪")
        break;
    case "2130037":
        this.$store.commit('setWeatherName', "北海道")
        break;
    case "2130656":
        this.$store.commit('setWeatherName', "青森")
        break;
    case "2113124":
        this.$store.commit('setWeatherName', "秋田")
        break;
    case "2112518":
        this.$store.commit('setWeatherName', "岩手")
        break;
    case "2111888":
        this.$store.commit('setWeatherName', "宮城")
        break;
    case "2110554":
        this.$store.commit('setWeatherName', "山形")
        break;
    case "2112922":
        this.$store.commit('setWeatherName', "福島")
        break;
    case "1855429":
        this.$store.commit('setWeatherName', "新潟")
        break;
    case "1850310":
        this.$store.commit('setWeatherName', "栃木")
        break;
    case "1863501":
        this.$store.commit('setWeatherName', "群馬")
        break;
    case "1853226":
        this.$store.commit('setWeatherName', "埼玉")
        break;
    case "2113014":
        this.$store.commit('setWeatherName', "千葉")
        break;
    case "1860291":
        this.$store.commit('setWeatherName', "神奈川")
        break;
    case "1849872":
        this.$store.commit('setWeatherName', "富山")
        break;
    case "1856210":
        this.$store.commit('setWeatherName', "長野")
        break;
    case "1848649":
        this.$store.commit('setWeatherName', "山梨")
        break;
    case "1861387":
        this.$store.commit('setWeatherName', "石川")
        break;
    case "1863640":
        this.$store.commit('setWeatherName', "岐阜")
        break;
    case "1851715":
        this.$store.commit('setWeatherName', "静岡")
        break;
    case "1865694":
        this.$store.commit('setWeatherName', "愛知")
        break;
    case "1863983":
        this.$store.commit('setWeatherName', "福井")
        break;
    case "1852553":
        this.$store.commit('setWeatherName', "滋賀")
        break;
    case "1857910":
        this.$store.commit('setWeatherName', "京都")
        break;
    case "1857352":
        this.$store.commit('setWeatherName', "三重")
        break;
    case "1862047":
        this.$store.commit('setWeatherName', "兵庫")
        break;
    case "1855608":
        this.$store.commit('setWeatherName', "奈良")
        break;
    case "1848938":
        this.$store.commit('setWeatherName', "和歌山")
        break;
    case "1849890":
        this.$store.commit('setWeatherName', "鳥取")
        break;
    case "1854381":
        this.$store.commit('setWeatherName', "岡山")
        break;
    case "1860834":
        this.$store.commit('setWeatherName', "香川")
        break;
    case "1850157":
        this.$store.commit('setWeatherName', "徳島")
        break;
    case "1852442":
        this.$store.commit('setWeatherName', "島根")
        break;
    case "1862413":
        this.$store.commit('setWeatherName', "広島")
        break;
    case "1859133":
        this.$store.commit('setWeatherName', "高知")
        break;
    case "1848681":
        this.$store.commit('setWeatherName', "山口")
        break;
    case "1864226":
        this.$store.commit('setWeatherName', "愛媛")
        break;
    case "1863958":
        this.$store.commit('setWeatherName', "福岡")
        break;
    case "1854484":
        this.$store.commit('setWeatherName', "大分")
        break;
    case "1853299":
        this.$store.commit('setWeatherName', "佐賀")
        break;
    case "1858419":
        this.$store.commit('setWeatherName', "熊本")
        break;
    case "1856710":
        this.$store.commit('setWeatherName', "宮崎")
        break;
    case "1856156":
        this.$store.commit('setWeatherName', "長崎")
        break;
    case "1860825":
        this.$store.commit('setWeatherName', "鹿児島")
        break;
    case "1854345":
        this.$store.commit('setWeatherName', "沖縄")
        break;
  }
  alert("天候チェックを" + this.$store.state.weatherName + "に設定しました")
    },
    hokkaido(){
    this.$router.push('hokkaido')
  },
  kanto(){
    this.$router.push('kanto')
  },
      touhoku(){
    this.$router.push('touhoku')
  },
  tyubu(){
    this.$router.push('tyubu')
  },
      kinki(){
    this.$router.push('kinki')
  },
  tyugoku(){
    this.$router.push('tyugoku')
  },
      sikoku(){
    this.$router.push('sikoku')
  },
  kyusyu(){
    this.$router.push('kyusyu')
  },
  etc(){
    this.$router.push('etc')
  },
  test () {
    this.$store.commit('setWeather', this.weather)
switch( this.weather ) {
    case "2112669":
        this.$store.commit('setWeatherName', "茨城")
        break;
    case "1850147":
        this.$store.commit('setWeatherName', "東京")
        break;
    case "1853904":
        this.$store.commit('setWeatherName', "大阪")
        break;
    case "2130037":
        this.$store.commit('setWeatherName', "北海道")
        break;
    case "2130656":
        this.$store.commit('setWeatherName', "青森")
        break;
    case "2113124":
        this.$store.commit('setWeatherName', "秋田")
        break;
    case "2112518":
        this.$store.commit('setWeatherName', "岩手")
        break;
    case "2111888":
        this.$store.commit('setWeatherName', "宮城")
        break;
    case "2110554":
        this.$store.commit('setWeatherName', "山形")
        break;
    case "2112922":
        this.$store.commit('setWeatherName', "福島")
        break;
    case "1855429":
        this.$store.commit('setWeatherName', "新潟")
        break;
    case "1850310":
        this.$store.commit('setWeatherName', "栃木")
        break;
    case "1863501":
        this.$store.commit('setWeatherName', "群馬")
        break;
    case "1853226":
        this.$store.commit('setWeatherName', "埼玉")
        break;
    case "2113014":
        this.$store.commit('setWeatherName', "千葉")
        break;
    case "1860291":
        this.$store.commit('setWeatherName', "神奈川")
        break;
    case "1849872":
        this.$store.commit('setWeatherName', "富山")
        break;
    case "1856210":
        this.$store.commit('setWeatherName', "長野")
        break;
    case "1848649":
        this.$store.commit('setWeatherName', "山梨")
        break;
    case "1861387":
        this.$store.commit('setWeatherName', "石川")
        break;
    case "1863640":
        this.$store.commit('setWeatherName', "岐阜")
        break;
    case "1851715":
        this.$store.commit('setWeatherName', "静岡")
        break;
    case "1865694":
        this.$store.commit('setWeatherName', "愛知")
        break;
    case "1863983":
        this.$store.commit('setWeatherName', "福井")
        break;
    case "1852553":
        this.$store.commit('setWeatherName', "滋賀")
        break;
    case "1857910":
        this.$store.commit('setWeatherName', "京都")
        break;
    case "1857352":
        this.$store.commit('setWeatherName', "三重")
        break;
    case "1862047":
        this.$store.commit('setWeatherName', "兵庫")
        break;
    case "1855608":
        this.$store.commit('setWeatherName', "奈良")
        break;
    case "1848938":
        this.$store.commit('setWeatherName', "和歌山")
        break;
    case "1849890":
        this.$store.commit('setWeatherName', "鳥取")
        break;
    case "1854381":
        this.$store.commit('setWeatherName', "岡山")
        break;
    case "1860834":
        this.$store.commit('setWeatherName', "香川")
        break;
    case "1850157":
        this.$store.commit('setWeatherName', "徳島")
        break;
    case "1852442":
        this.$store.commit('setWeatherName', "島根")
        break;
    case "1862413":
        this.$store.commit('setWeatherName', "広島")
        break;
    case "1859133":
        this.$store.commit('setWeatherName', "高知")
        break;
    case "1848681":
        this.$store.commit('setWeatherName', "山口")
        break;
    case "1864226":
        this.$store.commit('setWeatherName', "愛媛")
        break;
    case "1863958":
        this.$store.commit('setWeatherName', "福岡")
        break;
    case "1854484":
        this.$store.commit('setWeatherName', "大分")
        break;
    case "1853299":
        this.$store.commit('setWeatherName', "佐賀")
        break;
    case "1858419":
        this.$store.commit('setWeatherName', "熊本")
        break;
    case "1856710":
        this.$store.commit('setWeatherName', "宮崎")
        break;
    case "1856156":
        this.$store.commit('setWeatherName', "長崎")
        break;
    case "1860825":
        this.$store.commit('setWeatherName', "鹿児島")
        break;
    case "1854345":
        this.$store.commit('setWeatherName', "沖縄")
        break;
  }
  alert("設定を保存しました")
  }
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, main, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video, button{
	margin:0;
	padding:0;
	border: 0;
	/* font-size: 100%; */
}
  .hello{
      text-align:center;
  }
  .tetudo{
      display: grid;
      width:100vw;
              grid-template-columns: repeat(10,10%);
        grid-template-rows: repeat(10,10%);
        max-width:500px;
      margin:auto;
  }
  .tetudo img{
    grid-row:1/11;
    grid-column:1/11;
    z-index:1;
  }
  .hokkaido{
    grid-row:2/3;
    grid-column:6/8;
    z-index:2;
  }
  .touhoku{
    grid-row:4/5;
    grid-column:8/10;
    z-index:2;
  }
  .kanto{
    grid-row:6/7;
    grid-column:8/10;
    z-index:2;
  }
  .tyubu{
    grid-row:5/6;
    grid-column:5/7;
    z-index:2;
  }
  .kinki{
    grid-row:7/8;
    grid-column:5/7;
    z-index:2;
  }
  .tyugoku{
    grid-row:7/8;
    grid-column:2/4;
    z-index:2;
  }
  .sikoku{
    grid-row:9/10;
    grid-column:4/6;
    z-index:2;
  }
  .kyusyu{
    grid-row:9/10;
    grid-column:1/3;
    z-index:2;
  }
    .etc{
    grid-row:2/4;
    grid-column:2/4;
    z-index:2;
  }
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
   /* button{
 width:150px;
 height:30px;
 line-height:30px;
 text-align:center;  display: flex;     justify-content: center;     align-items: center;
 display:inline-block;
 background:#9b4dca;
 color:#fff;
 border-radius:5px;
 text-decoration:none;
 margin-top:3px;
  } */
</style>
