<template>
  <div class="main animated fadeIn">
    <img src="../assets/play.png" class="youtube" @click="tienonsei" v-if="hisyo === 0">
    <!-- <i class="youtube fab fa-youtube"></i> -->
    <img src="../assets/ojigi6.gif" class="hisyo" @click="tienonsei" v-if="hisyo === 0">
    <img src="../assets/ojigi9.gif" class="hisyo" v-if="hisyo === 1">
    <img src="../assets/ojigiB1.gif" class="hisyo" @click="tienonsei" v-if="hisyo === 2">
    <img src="../assets/ojigiC1.gif" class="hisyo" @click="inu" v-if="hisyo === 3">
    <img src="../assets/zou2.png" class="hisyo" @click="inu" v-if="hisyo === 10">
    <!-- <img src="../assets/13069.jpg" class="hisyo" width="95%"> -->
    <div class="right">
    <!-- <h1 class="date">{{this.hiduke["month"]}}月{{this.hiduke["date"]}}日{{this.hiduke["day"]}}曜日</h1> -->
    <!-- <div class="button" @click="ai">設定を読み込む</div> -->
    <div class="tien" v-if='hyoji["tien"] === true'>
    <h2><img src="../assets/keikoku.png" width="25px" v-if='this.tienflag == true'>電車遅延</h2>
    <p class="tientyu" v-if='this.tienflag == true'>{{this.tien_rosen}}で遅延が発生しています!
    </p>
    <p v-if="this.$store.state.signflag == 0">ログインしていません。</p>
    <a target="_blank" href="https://www.tetsudo.com/traffic/">詳細(外部サイト※みんなでつくる鉄道コム様)</a>
    </div>
    <!-- これは天気のアイコンにするべきだろう -->
    <div class="weather" v-if='hyoji["weather"] === true'>
    <h2><img src="../assets/kasa.jpg" width="25px" v-if='this.weatherflag["rain"] == true'>
    <img src="../assets/yuki.jpg" width="25px" v-if='this.weatherflag["snow"] == true'>{{this.weatherName}}の天気</h2>
    <p v-if="this.weatherflag['rain'] === true" class="tientyu">雨が降りそうです。雨具のご用意を。<br></p>
    <p v-if="this.weatherflag['snow'] === true" class="tientyu">雪が降りそうです<br></p>
    <p v-if="this.$store.state.signflag == 0">ログインしていません。<br></p>
    <p v-if="this.$store.state.signflag == 1">以後約15時間の気温について<br>{{this.kion_message}}<br></p>
    <router-link to="/weather">詳細を表示する</router-link>
    </div>
    <div class="yotei" v-if='hyoji["yotei"] === true'>
    <h2>予定</h2>
    本日の予定:
    {{this.yotei["todo"]["yotei"]}}<br>
    明日の予定:
    {{this.yotei2["todo"]["yotei"]}}
    </div>
    <div class="news" v-if='hyoji["news"] === true'>
    <h2>ニュース</h2>
      <a target="_blank" :href="news[0]">{{news[1]}}</a><br>
      <a target="_blank" :href="news[2]">{{news[3]}}</a><br>
      <a target="_blank" :href="news[4]">{{news[5]}}</a><br>
      <a target="_blank" :href="news[6]">{{news[7]}}</a>
      <!-- <li v-for="newss in news">
    {{ newss }} -->
  </li>
    </div>
   <div class="fx" v-if='hyoji["fx"] === true'>
    <h2>為替</h2>
    <!-- {{ this.fx }} -->
    ドル円：{{this.fx["ドル円"]}}<br>
    ユーロ円：{{this.fx["ユーロ円"]}}<br>
    英ポンド円：{{this.fx["英ポンド円"]}}<br>
    豪ドル円：{{this.fx["豪ドル円"]}}<br>
    (※{{this.time}}時点)<br>
    </div>
       <div class="nikkei" v-if='hyoji["nikkei"] === true'>
    <h2>日経平均</h2>
    {{ this.nikkei["日経平均"] }}
    (※{{this.time}}時点)
    </div>
    <div class="otoku" v-if='hyoji["otoku"] === true'>
    <h2>お得情報</h2>
          <li v-for="otokus in otoku">
    {{ otokus }}
  </li>
    </div>

<!-- クリック時に音声再生するための設定 -->
<audio id="sound-file" preload="none">
	<source src="../assets/cursor1.mp3" type="audio/mp3">
</audio>
<audio id="sound-file1" preload="none">
	<source src="../assets/sassoku.mp3" type="audio/mp3">
</audio>
<!-- ログイン警告 -->
<audio id="logout" preload="none">
	<source src="../assets/logout.mp3" type="audio/mp3">
</audio>
<!-- 遅延 -->
<audio id="tetudou" preload="none">
	<source src="../assets/tetudou.mp3" type="audio/mp3">
</audio>
<audio id="heijyou" preload="none">
	<source src="../assets/heijyou.mp3" type="audio/mp3">
</audio>
<audio id="tientyu" preload="none">
	<source src="../assets/tientyu.mp3" type="audio/mp3">
</audio>

<audio id="sound-file5" preload="none">
	<source src="../assets/tenki.mp3" type="audio/mp3">
</audio>
<!-- 天気 -->
<audio id="weather" preload="none">
	<source src="../assets/weather.mp3" type="audio/mp3">
</audio>
<!-- 雨 -->
<audio id="ame" preload="none">
	<source src="../assets/ame.mp3" type="audio/mp3">
</audio>
<audio id="yuki" preload="none">
	<source src="../assets/yuki.mp3" type="audio/mp3">
</audio>
<audio id="amekakuritu" preload="none">
	<source src="../assets/amekakuritu.mp3" type="audio/mp3">
</audio>
<!-- 気温 -->
<audio id="kion" preload="none">
	<source src="../assets/kion.mp3" type="audio/mp3">
</audio>
<audio id="6ika" preload="none">
	<source src="../assets/6ika.mp3" type="audio/mp3">
</audio>
<audio id="11ika" preload="none">
	<source src="../assets/11ika.mp3" type="audio/mp3">
</audio>
<audio id="15ika" preload="none">
	<source src="../assets/15ika.mp3" type="audio/mp3">
</audio>
<audio id="20ika" preload="none">
	<source src="../assets/20ika.mp3" type="audio/mp3">
</audio>
<audio id="26ijyou" preload="none">
	<source src="../assets/26ijyou.mp3" type="audio/mp3">
</audio>
<audio id="kaiteki" preload="none">
	<source src="../assets/kaiteki.mp3" type="audio/mp3">
</audio>

<audio id="ohayo" preload="auto">
<source src="../assets/ohayo.mp3" type="audio/mp3">
</audio>
<audio id="honjitu" preload="auto">
<source src="../assets/honjitu.mp3" type="audio/mp3">
</audio>
<!-- 犬 -->
<audio id="wan" preload="none">
	<source src="../assets/wan1.mp3" type="audio/mp3">
</audio>
<audio id="wan2" preload="none">
	<source src="../assets/wan2.mp3" type="audio/mp3">
</audio>
<audio id="paon" preload="none">
	<source src="../assets/paon.mp3" type="audio/mp3">
</audio>
    </div>
  </div>
</template>

<script>
import {db} from '../plugins/firebase'
import firebase from 'firebase'
import axios from 'axios'
  export default {
    name: 'HelloWorld',
    data() {
      return {
        user:null,
        myset: "",
        myset_name: "test",
        tien:[],
        tien_rosen:[],
        tienflag:false,
        news:[],
        otoku:[],
        date:"",
        date2:"",
        hiduke:{
          year:"",
          month:"",
          date:"",
          day:""
        },
        hiduke2:{
          year:"",
          month:"",
          date:"",
          day:""
        },
        city: null, 
        temp: null,
        weather:[],
        weatherNo:"",
        weatherName:"東京",
        // 天気の警告用
        weatherflag:{
          // 雪か雨
          all:false,
          rain:false,
          snow:false
        },
        alert:{
          e1:"null"
        },
        yotei:{"todo":{"yotei":"入力されている予定はありません"}},
        yotei2:{"todo":{"yotei":"入力されている予定はありません"}},
        fx:[],
        time:"",
        nikkei:"",
        // 表示する秘書の画像管理用フラグ
        hisyo:null,
        inucount:0,
        hyoji:{
          fx: true,
          news: true,
          nikkei: true,
          otoku: true,
          tien: true,
          weather: true,
          yotei: true,
        },
kion_message:""
        }
    },
  created() {
    firebase.auth().onAuthStateChanged(user => {
  // ログイン状態ならuserが取得できる
  this.user = user ? user : {}
              if(this.user['uid'] != null){
                console.log("hisyo設定A")
                console.log(this.user['uid'])
              this.$store.commit('setuid', this.user['uid']),
              this.$store.commit('setSignflag', 1)
                  db.collection('user').doc(this.$store.state.uid).collection('hisyo').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.data());
      var fuga = doc.data()
      console.log("hisyoチェック")
      console.log(fuga)
      if(fuga["hisyo"] === undefined){
        this.hisyo = 0}else{
      this.hisyo = fuga["hisyo"]
        }
    });
});
    // 日付をnew
    var date2 = new Date();
    var year = date2.getFullYear();
    this.hiduke["year"] = date2.getFullYear();
    // 月日をhidukeオブジェクトに
    this.hiduke["month"] = date2.getMonth()+1;
    var month = date2.getMonth()+1;
    this.hiduke["date"] = date2.getDate();
    var date = date2.getDate();
    // 曜日配列を作り、それをdayへ代入
    const dayT = ["日","月","火","水","木","金","土"]
    this.hiduke["day"] = dayT[date2.getDay()];
    // 予定管理用変数宣言
    var hoge = []
    var hoge2 = null
    var hoge3 = null
    // signflagでサインインチェックをしていた時の名残、不要？
    // if(this.$store.state.signflag === 0){
    //   this.hisyo = 0
    // }
    // サインインしているか判断し、サインイン中なら表示非表示設定を読み込む
    if(this.$store.state.signflag === 1){
    db.collection('user').doc(this.$store.state.uid).collection('hyoji').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.data());
      var fuga = doc.data()
      this.hyoji = fuga["hyoji"]
            console.log(fuga["hyoji"]);
    });
});
    }
    // 予定を読み込む
    if(this.$store.state.signflag === 1){
    var hiduke = String(this.hiduke["year"] * 10000 + this.hiduke["month"] * 100 + this.hiduke["date"])
    var date_asu = new Date();
    date_asu.setDate(date_asu.getDate() + 1);
    var year2 = date_asu.getFullYear();
    this.hiduke2["year"] = date_asu.getFullYear();
    // 月日をhidukeオブジェクトに
    this.hiduke2["month"] = date_asu.getMonth()+1;
    // var month = date2.getMonth()+1;
    this.hiduke2["date"] = date_asu.getDate();
    // var date = date2.getDate();
    var date_asu2 = String(this.hiduke2["year"] * 10000 + this.hiduke2["month"] * 100 + this.hiduke2["date"])
console.log(date_asu2)
    db.collection('user').doc(this.$store.state.uid).collection('yotei').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.id, " => ", doc.data());
      console.log(hiduke);
      if(doc.id == hiduke){
        this.yotei = doc.data()
      }
      if(doc.id == date_asu2){
        this.yotei2 = doc.data()
      }
    });
});
    }

    // 遅延情報
    // データベースに登録した「遅延を確認するエリア」と、「利用する路線の情報」を取得する
    if(this.$store.state.signflag === 1){
    db.collection('user').doc(this.$store.state.uid).collection('rosen').doc('rosen').get().then((doc) => {
      if (doc.exists) {
        var tien = doc.data()
        this.$store.state.rosen = tien["rosen"]
        console.log(this.$store.state.rosen)        
      }
    }).catch(function(error) {
    console.log("Error getting document:", error);
}).then(() => {
  // 遅延している路線リストを取得する
      db.collection('test').doc('9Y7ljL1Yatuali0erQN2').get().then((doc) => {
    if (doc.exists) {
        console.log("Document data:", doc.data());
        let i = doc.data()
        this.myset = i['test']
        console.log(i['test'])
        console.log("now")
      // 遅延している路線リストはスクレイピングで取得した文字列になっている。そのためJSON形式に変換しようと考えた
        let json = JSON.parse(i['test'])
        console.log(json)
        console.log("形式チェックします")
        this.$store.state.rosen2 = json
          console.log(this.$store.state.rosen)    
  console.log(this.$store.state.rosen2)
  // 遅延情報を１つずつ取り出し
for(var hoge = 0; hoge < this.$store.state.rosen2.length; hoge++){
    // 利用路線と照合。一致した場合は利用路線に遅延が発生。flagをtrueにする
    for(var hogehoge = 0; hogehoge < this.$store.state.rosen.length; hogehoge++){
      console.log(this.$store.state.rosen[hogehoge])
      console.log(this.$store.state.rosen2[hoge]["name"])
      if(this.$store.state.rosen[hogehoge] == this.$store.state.rosen2[hoge]["name"]){
        this.tienflag = true
        this.tien_rosen.push(this.$store.state.rosen[hogehoge])
        console.log(this.tien_rosen)
      }
    }
}
} // this.mysetcount = i['test'].length
     else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
})
})
    }

    // 天気設定を読み込む
        if(this.$store.state.signflag === 1){
    db.collection('user').doc(this.$store.state.uid).collection('weather').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.data());
      var fuga = doc.data()
      this.weatherNo = fuga["weather"]
      console.log(this.weatherNo)
      this.weatherName = fuga["weatherName"]
      // 天気ページ用に地方IDと地方名をstoreに渡す
      this.$store.commit('setWeather', fuga["weather"])
      this.$store.commit('setWeatherName', fuga["weatherName"])
      // this.w = fuga["hyoji"]
      //       console.log(fuga["hyoji"]);
    });
}).then(() => {
// http://api.openweathermap.org/data/2.5/forecast?id=1853904&APPID=0a8f60c07e0ec92c23a485ee7f9f4c94
console.log(this.weatherNo)
  var weatherurl = "https://api.openweathermap.org/data/2.5/forecast?id=" + this.$store.state.weather + "&units=metric&APPID=0a8f60c07e0ec92c23a485ee7f9f4c94"
   axios.get(weatherurl)
   .then(function(response){
     this.weather.push(response.data.list[0])
     this.weather.push(response.data.list[1])
     this.weather.push(response.data.list[2])
     this.weather.push(response.data.list[3])
     this.weather.push(response.data.list[4])
     this.weather.push(response.data.list[5])
     this.weather.push(response.data.list[6])
     this.weather.push(response.data.list[7])
     var aaa = response.data.list[0]["weather"]["0"]["main"]
    //  天気フラグ操作
    for( var weathercount = 0; weathercount < 8; weathercount++ ){
      console.log(response.data.list[weathercount]["weather"]["0"]["main"])
  if(response.data.list[weathercount]["weather"]["0"]["main"] == "Snow"){
       this.weatherflag["snow"] = true
       this.weatherflag["all"] = true
     }
       if(response.data.list[weathercount]["weather"]["0"]["main"] == "Rain"){
       this.weatherflag["rain"] = true
       this.weatherflag["all"] = true
       }
}
if(this.weather[3]["main"]["temp"] < 6 || this.weather[4]["main"]["temp"] < 6 ||
 this.weather[5]["main"]["temp"] < 6 || this.weather[6]["main"]["temp"] < 6 || this.weather[7]["main"]["temp"] < 6){
  console.log("6ika")
  this.kion_message = "6度以下になりそうです。寒さの対策を万全にして下さい"
  console.log(this.kion_message)
}else{
  if(this.weather[3]["main"]["temp"] < 11 || this.weather[4]["main"]["temp"] < 11 ||
 this.weather[5]["main"]["temp"] < 11 || this.weather[6]["main"]["temp"] < 11 || this.weather[7]["main"]["temp"] < 11){
  this.kion_message = "7度～11度になりそうです。コートなどが必要でしょう"
}else{
    if(this.weather[3]["main"]["temp"] < 15 || this.weather[4]["main"]["temp"] < 15 ||
 this.weather[5]["main"]["temp"] < 15 || this.weather[6]["main"]["temp"] < 15 || this.weather[7]["main"]["temp"] < 15){
  this.kion_message = "12度～15度になりそうです。軽めのアウターなどがあると良いでしょう"
}else{
    if(this.weather[3]["main"]["temp"] < 20 || this.weather[4]["main"]["temp"] < 20 ||
 this.weather[5]["main"]["temp"] < 20 || this.weather[6]["main"]["temp"] < 20 || this.weather[7]["main"]["temp"] < 20){
  this.kion_message = "16度～20度になりそうです。やや肌寒いでしょうか。寒さが苦手な方はご注意下さい。"
}else{
    if(this.weather[3]["main"]["temp"] > 26 || this.weather[4]["main"]["temp"] > 26 ||
 this.weather[5]["main"]["temp"] > 26 || this.weather[6]["main"]["temp"] > 26 || this.weather[7]["main"]["temp"] > 26){
  this.kion_message = "26度以上になりそうです。半袖が良いでしょう。"
}else{
  this.kion_message = "21度～25度になりそうです。快適な気温です。特に気温は意識しなくて良いでしょう。"
}
}
}
}
}
   }.bind(this))
   .catch(function(error){
     console.log(error)
   })
  })}
              }else{
                this.hisyo = 0
                this.yotei["todo"]["yotei"] = "ログインしていません"
                this.yotei2["todo"]["yotei"] = "ログインしていません"
                }
})
    // 現在時刻をdatatimeへ
    db.collection('test').doc('U6ZKO8Ro4j1GV4l9h6V1').get().then((doc) => {
    if (doc.exists) {
        console.log("Document data:", doc.data());
        let i = doc.data()
        this.time = i["time"]
} // this.mysetcount = i['test'].length
     else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
})    
    // 為替情報をdatafxへ
    db.collection('test').doc('3bOZEMBTGW9nibZ3HMgG').get().then((doc) => {
    if (doc.exists) {
        console.log("Document data:", doc.data());
        let i = doc.data()
        this.fx = i
        console.log(i)
        console.log("fx")
} // this.mysetcount = i['test'].length
     else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
})
    // 日経平均をnikkeiへ
    db.collection('test').doc('BNYuzhEZjuNVGD4rjSsf').get().then((doc) => {
    if (doc.exists) {
        console.log("Document data:", doc.data());
        let i = doc.data()
        this.nikkei = i
} // this.mysetcount = i['test'].length
     else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
})
// ニュースを拾ってくる
      db.collection('test').doc('RnEdzOTdqjBYHy3UJB84').get().then((doc) => {
    if (doc.exists) {
        console.log("Document data:", doc.data());
        let b = doc.data()
        let c = b["news"]
        this.news = c
        // this.mysetcount = i['test'].length
    } else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
});
// お得情報を拾ってくる
      db.collection('test').doc('vrkfOtFk0EECMJeZPXW8').get().then((doc) => {
    if (doc.exists) {
        console.log("Document data:", doc.data());
        let d = doc.data()
        let e = d["otoku"]
        this.otoku = e
        // this.mysetcount = i['test'].length
    } else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
});},
methods: {
  test() {
    document.getElementById( 'sound-file' ).play()
  },
  tienonsei() {
        this.hisyo = 1
  if(this.$store.state.signflag == 0){
   var logout = document.getElementById( 'logout' );
   logout.play();
  }else{
  console.log(this.weather[0]["main"]["temp"])
  console.log("test")
  var a = document.getElementById( 'ohayo' );
  var b = document.getElementById( 'honjitu' );
  // 鉄道情報
  if(this.tienflag == true){
    console.log("tien")
    var c = document.getElementById( 'tientyu' );
  }else{
  var c = document.getElementById( 'heijyou' );
}
var tetudou = document.getElementById( 'tetudou' );
var weather = document.getElementById( 'weather' );
var kion = document.getElementById( 'kion' );
// 天気判断
if(this.weatherflag["rain"] === true){
  var d = document.getElementById( 'sound-file6' );
}else{
  if(this.weatherflag["snow"] === true){
  var d = document.getElementById( 'yuki' );
}else{
  var d = document.getElementById( 'amekakuritu' );
}
}
// 気温判断
if(this.weather[3]["main"]["temp"] < 6 || this.weather[4]["main"]["temp"] < 6 ||
 this.weather[5]["main"]["temp"] < 6 || this.weather[6]["main"]["temp"] < 6 || this.weather[7]["main"]["temp"] < 6){
  console.log("6ika")
  var kion2 = document.getElementById( '6ika' );
  this.kion_message = "6度以下です"
  console.log(this.kion_message)
}else{
  if(this.weather[3]["main"]["temp"] < 11 || this.weather[4]["main"]["temp"] < 11 ||
 this.weather[5]["main"]["temp"] < 11 || this.weather[6]["main"]["temp"] < 11 || this.weather[7]["main"]["temp"] < 11){
  var kion2 = document.getElementById( '11ika' );
}else{
    if(this.weather[3]["main"]["temp"] < 15 || this.weather[4]["main"]["temp"] < 15 ||
 this.weather[5]["main"]["temp"] < 15 || this.weather[6]["main"]["temp"] < 15 || this.weather[7]["main"]["temp"] < 15){
  var kion2 = document.getElementById( '15ika' );
}else{
    if(this.weather[3]["main"]["temp"] < 20 || this.weather[4]["main"]["temp"] < 20 ||
 this.weather[5]["main"]["temp"] < 20 || this.weather[6]["main"]["temp"] < 20 || this.weather[7]["main"]["temp"] < 20){
  var kion2 = document.getElementById( '20ika' );
}else{
    if(this.weather[3]["main"]["temp"] > 26 || this.weather[4]["main"]["temp"] > 26 ||
 this.weather[5]["main"]["temp"] > 26 || this.weather[6]["main"]["temp"] > 26 || this.weather[7]["main"]["temp"] > 26){
  var kion2 = document.getElementById( '26ijyou' );
}else{
  var kion2 = document.getElementById( 'kaiteki' );
}
}
}
}
}
  }
 kion.addEventListener("ended", function() {
    // 遅延案内
  kion2.play()
  });
 d.addEventListener("ended", function() {
    // 遅延案内
  kion.play()
  });
 weather.addEventListener("ended", function() {
    // 遅延案内
  d.play()
  });
 c.addEventListener("ended", function() {
    // 遅延案内
  weather.play()
  });
    tetudou.addEventListener("ended", function() {
    // 遅延案内
  c.play()
  });
  b.addEventListener("ended", function() {
    // 遅延案内
  tetudou.play()
  });
// 基本、おはよう→今日の情報
a.addEventListener("ended", function() {
b.play();
});
a.play();
},
inu() {
  this.inucount = this.inucount + 1
  var wan = document.getElementById( 'wan' );
  console.log(wan)
  if(this.inucount > 9){
    this.hisyo = 10
        var paon = document.getElementById( 'paon' );
    paon.play();
    }else{
    wan.play();
  } 
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
  .main{
    	display: grid;
	grid-template-columns: repeat(10,10%);
  }
  .hisyo{
    /* margin-left:-25%;
    margin-top:-20%; */
    grid-row:1/10;
    grid-column:1/5;
    max-width:100%;
    cursor: pointer;
  position: sticky;
  top:10px;
  
  }
  .date{
    grid-row:1;
    grid-column:5/11;
  }
  .tien{
    grid-row:2;
    grid-column:5/11;
  }
  .weather{
    grid-row:3;
    grid-column:5/11;
  }
  .yotei{
    grid-row:4;
    grid-column:5/11;
  }
  .news{
    grid-row:5;
    grid-column:5/11;
  }
  .otoku{
    grid-row:6;
    grid-column:5/11;
  }
  .etc{
    grid-row:8;
    grid-column:5/11;
  }
  .right{
    grid-row:1;
    grid-column:5/11;
  }
    .youtube{
    grid-row:1/10;
    grid-column:1/5;
    z-index:2;
    color:red;
    margin:3vw 3vw;
    width:6vw;
    cursor: pointer;
      position: sticky;
  top:20px;
  }
  .tientyu{
    color:red;
    font-weight:bold;
  }
</style>
