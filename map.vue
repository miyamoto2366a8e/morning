<template>
  <div class="hello animated fadeIn">
<div class="map">
<h1 class="title">選択してください。現在値:{{this.weatherName}}</h1>
<button class="back" @click="back">変更せずに戻る</button>
<div @click="weather = '2130037'; al($event)" class="hokkaido"><p class="txt">北海道</p></div>
<div @click="weather = '2130656'; al($event)" class="aomori"><p class="txt">青森</p></div>
<div @click="weather = '2113124'; al($event)" class="akita"><p class="txt">秋田</p></div>
<div @click="weather = '2112518'; al($event)" class="iwate"><p class="txt">岩手</p></div>
<div @click="weather = '2110554'; al($event)" class="yamagata"><p class="txt">山形</p></div>
<div @click="weather = '2111888'; al($event)" class="miyagi"><p class="txt">宮城</p></div>
<div @click="weather = '2112922'; al($event)" class="hukusima"><p class="txt">福島</p></div>
<div @click="weather = '2112669'; al($event)" class="ibaraki"><p class="txt">茨城</p></div>
<div @click="weather = '2113014'; al($event)" class="tiba"><p class="txt">千葉</p></div>
<div @click="weather = '1850310'; al($event)" class="totigi"><p class="txt">栃木</p></div>
<div @click="weather = '1863501'; al($event)" class="gunma"><p class="txt">群馬</p></div>
<div @click="weather = '1853226'; al($event)" class="saitama"><p class="txt">埼玉</p></div>
<div @click="weather = '1850147'; al($event)" class="toukyou"><p class="txt">東京</p></div>
<div @click="weather = '1860291'; al($event)" class="kanagawa"><p class="txt">神奈川</p></div>
<div @click="weather = '1855429'; al($event)" class="niigata"><p class="txt">新潟</p></div>
<div @click="weather = '1849872'; al($event)" class="toyama"><p class="txt">富山</p></div>
<div @click="weather = '1861387'; al($event)" class="isikawa"><p class="txt">石川</p></div>
<div @click="weather = '1863983'; al($event)" class="hukui"><p class="txt">福井</p></div>
<div @click="weather = '1856210'; al($event)" class="nagano"><p class="txt">長野</p></div>
<div @click="weather = '1848649'; al($event)" class="yamanasi"><p class="txt">山梨</p></div>
<div @click="weather = '1851715'; al($event)" class="sizuoka"><p class="txt">静岡</p></div>
<div @click="weather = '1863640'; al($event)" class="gihu"><p class="txt">岐阜</p></div>
<div @click="weather = '1865694'; al($event)" class="aiti"><p class="txt">愛知</p></div>
<div @click="weather = '1852553'; al($event)" class="siga"><p class="txt">滋賀</p></div>
<div @click="weather = '1857352'; al($event)" class="mie"><p class="txt">三重</p></div>
<div @click="weather = '1857910'; al($event)" class="kyouto"><p class="txt">京都</p></div>
<div @click="weather = '1855608'; al($event)" class="nara"><p class="txt">奈良</p></div>
<div @click="weather = '1853904'; al($event)" class="oosaka"><p class="txt">大阪</p></div>
<div @click="weather = '1848938'; al($event)" class="wakayama"><p class="txt">和歌山</p></div>
<div @click="weather = '1862047'; al($event)" class="hyougo"><p class="txt">兵庫</p></div>
<div @click="weather = '1849890'; al($event)" class="tottori"><p class="txt">鳥取</p></div>
<div @click="weather = '1854381'; al($event)" class="okayama"><p class="txt">岡山</p></div>
<div @click="weather = '1852442'; al($event)" class="simane"><p class="txt">島根</p></div>
<div @click="weather = '1862413'; al($event)" class="hirosima"><p class="txt">広島</p></div>
<div @click="weather = '1848681'; al($event)" class="yamaguti"><p class="txt">山口</p></div>
<div @click="weather = '1860834'; al($event)" class="kagawa"><p class="txt">香川</p></div>
<div @click="weather = '1850157'; al($event)" class="tokusima"><p class="txt">徳島</p></div>
<div @click="weather = '1864226'; al($event)" class="ehime"><p class="txt">愛媛</p></div>
<div @click="weather = '1859133'; al($event)" class="kouti"><p class="txt">高知</p></div>
<div @click="weather = '1863958'; al($event)" class="hukuoka"><p class="txt">福岡</p></div>
<div @click="weather = '1854484'; al($event)" class="ooita"><p class="txt">大分</p></div>
<div @click="weather = '1856710'; al($event)" class="miyazaki"><p class="txt">宮崎</p></div>
<div @click="weather = '1858419'; al($event)" class="kumamoto"><p class="txt">熊本</p></div>
<div @click="weather = '1860825'; al($event)" class="kagosima"><p class="txt">鹿児島</p></div>
<div @click="weather = '1853299'; al($event)" class="saga"><p class="txt">佐賀</p></div>
<div @click="weather = '1856156'; al($event)" class="nagasaki"><p class="txt">長崎</p></div>
<div @click="weather = '1854345'; al($event)" class="okinawa"><p class="txt">沖縄</p></div>
</div>
  </div>
</template>

<script>
import {db} from '../plugins/firebase';
import firebase from 'firebase'
  export default {
    name: 'conf',
    data() {
      return {
        weather:"",
        weatherName:""
      }
    },
  created() {
          if(this.$store.state.signflag == 0){
  alert("ログインしていません")
  this.$router.push('/sign')
}
  },
  methods: {
      al(){
        //   コレをfirebase書き込みに変更する、storeはいじらなくていい（helloworldはfirebaseを読み込むため）
    //   this.$store.commit('setWeather', this.weather)

switch( this.weather ) {
    case "2112669":
        this.weatherName = "茨城"
        break;
    case "1850147":
        this.weatherName = "東京"
        break;
    case "1853904":
        this.weatherName = "大阪"
        break;
    case "2130037":
        this.weatherName = "北海道"
        break;
    case "2130656":
        this.weatherName = "青森"
        break;
    case "2113124":
        this.weatherName = "秋田"
        break;
    case "2112518":
        this.weatherName = "岩手"
        break;
    case "2111888":
        this.weatherName = "宮城"
        break;
    case "2110554":
        this.weatherName = "山形"
        break;
    case "2112922":
        this.weatherName = "福島"
        break;
    case "1855429":
        this.weatherName = "新潟"
        break;
    case "1850310":
        this.weatherName = "栃木"
        break;
    case "1863501":
        this.weatherName = "群馬"
        break;
    case "1853226":
        this.weatherName = "埼玉"
        break;
    case "2113014":
        this.weatherName = "千葉"
        break;
    case "1860291":
        this.weatherName = "神奈川"
        break;
    case "1849872":
        this.weatherName = "富山"
        break;
    case "1856210":
        this.weatherName = "長野"
        break;
    case "1848649":
        this.weatherName = "山梨"
        break;
    case "1861387":
        this.weatherName = "石川"
        break;
    case "1863640":
        this.weatherName = "岐阜"
        break;
    case "1851715":
        this.weatherName = "静岡"
        break;
    case "1865694":
        this.weatherName = "愛知"
        break;
    case "1863983":
        this.weatherName = "福井"
        break;
    case "1852553":
        this.weatherName = "滋賀"
        break;
    case "1857910":
        this.weatherName = "京都"
        break;
    case "1857352":
        this.weatherName = "三重"
        break;
    case "1862047":
        this.weatherName = "兵庫"
        break;
    case "1855608":
        this.weatherName = "奈良"
        break;
    case "1848938":
        this.weatherName = "和歌山"
        break;
    case "1849890":
        this.weatherName = "鳥取"
        break;
    case "1854381":
        this.weatherName = "岡山"
        break;
    case "1860834":
        this.weatherName = "香川"
        break;
    case "1850157":
        this.weatherName = "徳島"
        break;
    case "1852442":
        this.weatherName = "島根"
        break;
    case "1862413":
        this.weatherName = "広島"
        break;
    case "1859133":
        this.weatherName = "高知"
        break;
    case "1848681":
        this.weatherName = "山口"
        break;
    case "1864226":
        this.weatherName = "愛媛"
        break;
    case "1863958":
        this.weatherName = "福岡"
        break;
    case "1854484":
        this.weatherName = "大分"
        break;
    case "1853299":
        this.weatherName = "佐賀"
        break;
    case "1858419":
        this.weatherName = "熊本"
        break;
    case "1856710":
        this.weatherName = "宮崎"
        break;
    case "1856156":
        this.weatherName = "長崎"
        break;
    case "1860825":
        this.weatherName = "鹿児島"
        break;
    case "1854345":
        this.weatherName = "沖縄"
        break;
  }
           db.collection('user').doc(this.$store.state.uid).collection('weather').doc('weather').set({
         weather: this.weather,
         weatherName: this.weatherName
          });
  alert("天候チェックを" + this.weatherName + "に設定しました")
    },
  test () {
    this.$store.commit('setWeather', this.weather)
    switch( this.weather ) {
  }
  },
  back(){
      this.$router.push('/conf')
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
.map{
    width:100%;
    display: grid;
    /* grid-template-columns: repeat(22,4.545454%); */
        grid-template-columns: repeat(25,4%);
        grid-template-rows: repeat(19,5vw);
}
.title{
    grid-row:2/4;
    grid-column:2/19;
}
.back{
    grid-row:5/7;
    grid-column:2/10;
}
.hokkaido{
    background-color:blue;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:2/5;
    grid-column:20/25;
}
.aomori{
    background-color:aqua;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:6/7;
	grid-column:20/24;
}
.akita{
    background-color:aqua;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:7/8;
	grid-column:20/22;
}
.iwate{
    background-color:aqua;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:7/8;
	grid-column:22/24;
}
.yamagata{
    background-color:aqua;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:8/9;
	grid-column:20/22;
}
.miyagi{
    background-color:aqua;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:8/9;
	grid-column:22/24;
}
.hukusima{
    background-color:aqua;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:9/10;
	grid-column:21/24;
}
.ibaraki{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/12;
	grid-column:23/24;
}
.tiba{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:12/16;
	grid-column:23/24;
}
.gunma{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/11;
	grid-column:19/21;
}
.totigi{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/11;
	grid-column:21/23;
}
.saitama{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:11/12;
	grid-column:19/23;
}
.toukyou{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:12/14;
	grid-column:20/23;
}
.kanagawa{
    background-color:lime;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:14/16;
	grid-column:19/22;
}
.niigata{
    background-color:green;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:9/10;
	grid-column:18/21;
}
.toyama{
    background-color:green;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:9/10;
	grid-column:16/18;
}
.isikawa{
    background-color:green;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:8/10;
	grid-column:15/16;
}
.hukui{
    background-color:green;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/11;
	grid-column:13/16;
}
.nagano{
    background-color:teal;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/14;
	grid-column:17/19;
}
.yamanasi{
    background-color:teal;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:12/14;
	grid-column:19/20;
}
.sizuoka{
    background-color:teal;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:14/16;
	grid-column:18/19;
}
.gihu{
    background-color:teal;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/14;
	grid-column:16/17;
}
.aiti{
    background-color:teal;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:14/16;
	grid-column:16/18;
}
.siga{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:11/13;
	grid-column:15/16;
}
.kyouto{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:11/13;
	grid-column:13/15;
}
.wakayama{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:16/17;
	grid-column:13/16;
}
.hyougo{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/14;
	grid-column:12/13;
}
.tottori{
    background-color:orange;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/12;
	grid-column:11/12;
}
.okayama{
    background-color:orange;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:12/14;
	grid-column:11/12;
}
.simane{
    background-color:orange;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/12;
	grid-column:10/11;
}
.hirosima{
    background-color:orange;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:12/14;
	grid-column:10/11;
}
.yamaguti{
    background-color:orange;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/14;
	grid-column:9/10;
}
.ehime{
    background-color:#FF3399;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:15/16;
	grid-column:9/11;
}
.kagawa{
    background-color:#FF3399;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:15/16;
	grid-column:11/13;
}
.kouti{
    background-color:#FF3399;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:16/17;
	grid-column:9/11;
}
.tokusima{
    background-color:#FF3399;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:16/17;
	grid-column:11/13;
}
.ooita{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/13;
	grid-column:7/8;
}
.hukuoka{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/13;
	grid-column:5/7;
}
.saga{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/13;
	grid-column:4/5;
}
.nagasaki{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:10/13;
	grid-column:3/4;
}
.kagosima{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:15/17;
	grid-column:5/8;
}
.okinawa{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:18/20;
	grid-column:5/6;
}
.kumamoto{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:13/15;
	grid-column:5/7;
}
.miyazaki{
    background-color:pink;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:13/15;
	grid-column:7/8;
}
.mie{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:13/16;
	grid-column:15/16;
}
.nara{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:13/16;
	grid-column:14/15;
}
.oosaka{
    background-color:#FFCC33;
    margin:0.3vw; cursor : pointer; text-align:center;  display: flex;     justify-content: center;     align-items: center;
    grid-row:13/16;
	grid-column:13/14;
}
.txt{
    margin:auto;
    color:black;
    text-shadow: white 1px 1px 0px, white -1px 1px 0px,
             white 1px -1px 0px, white -1px -1px 0px;
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
   button{
  }
</style>
