<template>
  <div class="hello animated fadeIn">
    {{this.value1}}
      <div class="block">
    <span class="demonstration">日付を選択して下さい</span><br>
    <el-date-picker
      v-model="value1"
      type="date"
      placeholder="Pick a day">
    </el-date-picker>

        <!-- <el-form-item label="Activity form">
    <el-input type="textarea" v-model="form.desc"></el-input>
  </el-form-item> -->
    <p class="error" v-if="errorflag == 1">{{this.error}}</p>
     <!-- <video muted loop id="video"><source src="../assets/13087.mp4"></video> -->
    <br>内容<br>
    <input type="text" name="example2" v-model="todo['yotei']"><br>
    <p><button @click="addmyset">予定を保存</button></p>
    現在の予定一覧
    <table class="yotei" v-for="(dbs, index) in db">
      <tr><th>
  <input type="checkbox" v-model="delete_select" v-bind:value="index"></th>
        <th>{{ dbs }}</th>
  </tr>
  </table>
<button @click="del">選択した予定を削除</button>
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
        errorflag: 0,
        error:"エラーメッセージテスト",
        sabadata:null,
        todo: {
          year:null,
          month:null,
          date:null,
          yotei:null
      },
        month_date:null,
      test:"1234",
      db: null,
      delete_select:[],
      index:[],
      value1:null
      }
    },
  created() {
    if(this.$store.state.signflag == 0){
  alert("ログインしていません")
  this.$router.push('/sign')
}
  // 現在の予定を取得して一覧表示します
  var hoge = []
    var hoge2 = null
    var hoge3 = null
    db.collection('user').doc(this.$store.state.uid).collection('yotei').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.id, " => ", doc.data());
      // 削除用にドキュメント名であるＩＤだけを入れた配列を作ります。
      this.index.push(doc.id)
      hoge2 = doc.data()['todo']['year'] + "年" + doc.data()['todo']['month'] + "月" + doc.data()['todo']['date'] + "日" + ":"
      hoge3 = doc.data()['todo']['yotei']
        hoge.push(hoge2 + hoge3)
        console.log(hoge)
        console.log(hoge2)
        this.$store.commit('setDB', hoge)
        this.db = hoge
        console.log(this.$store.state.db)
    });
});
  },
  methods: {
  // アプリを終了するとき動画を再生するテスト
  syuryo(){
    console.log("testmethods")
    var v = document.getElementById("video");
    v.play();
    // 月日予定をファイアーベースに登録する
  },
  addmyset() {
      // 未入力チェック
      if(this.value1 == null){
        this.error = "日付が選択されていません"
        this.errorflag = 1
        }else{
      if(this.todo["yotei"] == null){this.error = "予定が入力されていません"}else{
        // monthとdateを繋げる
        var date = String(this.value1)
        console.log(date)
        var mon = date.substr(4, 3)
        var month = 0
        switch( mon ) {
    case "Jan":
        month = "01"
        break;
    case "Feb":
        month = "02"
        break;
    case "Mar":
        month = "03"
        break;
    case "Apr":
        month = "04"
        break;
    case "May":
        month = "05"
        break;
    case "Jun":
        month = "06"
        break;
    case "Jul":
        month = "07"
        break;
    case "Aug":
        month = "08"
        break;
    case "Sep":
        month = "09"
        break;
    case "Oct":
        month = "10"
        break;
    case "Nov":
        month = "11"
        break;
    case "Dec":
        month = "12"
        break;
        }
      this.todo["month"] = month
      this.todo["date"] = date.substr(8, 2)
      this.todo["year"] = date.substr(11, 4)
      console.log(this.todo["year"])
      this.month_date = String(this.todo["year"] + month + this.todo["date"])
      console.log(this.month_date)
        // userコレクションにuidドキュメントを作り、その中にyoteiコレクションを作る。
        // さらにその中に日付でドキュメントを作り、その中に予定を入れる。
         db.collection('user').doc(this.$store.state.uid).collection('yotei').doc(this.month_date).set({
         todo: this.todo
          });
        // 入れた後データを読み込む
        // 初期化
          var hoge = []
    var hoge2 = null
    var hoge3 = null
    db.collection('user').doc(this.$store.state.uid).collection('yotei').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.id, " => ", doc.data());
      // 削除用にドキュメント名であるＩＤだけを入れた配列を作ります。
      this.index.push(doc.id)
      hoge2 = doc.data()['todo']['year'] + "年" + doc.data()['todo']['month'] + "月" + doc.data()['todo']['date'] + "日" + ":"
      hoge3 = doc.data()['todo']['yotei']
        hoge.push(hoge2 + hoge3)
        console.log(hoge)
        console.log(hoge2)
        this.$store.commit('setDB', hoge)
        this.db = hoge
        console.log(this.$store.state.db)
    });
});
    alert("設定を保存しました")
      }}},
    del() {
      // OK.例：[0,3]
      console.log(this.delete_select.length)
      for(var i = 0; i < this.delete_select.length; i++){
      var test = this.delete_select[i]
      console.log("indexの[i]番目", test)
      db.collection("user").doc(this.$store.state.uid).collection('yotei').doc(this.index[test]).delete().then(function() {
    console.log("Document successfully deleted!");
}).catch(function(error) {
    console.error("Error removing document: ", error);
});
      }
      // 変更したため、予定を読み直します
       var hoge = []
    var hoge2 = null
    var hoge3 = null 
        db.collection('user').doc(this.$store.state.uid).collection('yotei').get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.id, " => ", doc.data());
      // indexに値が入っているので初期化
      this.index = []
      this.index.push(doc.id)
      hoge2 = doc.data()['todo']['month'] + "月" + doc.data()['todo']['date'] + "日" + ":"
      hoge3 = doc.data()['todo']['yotei']
        hoge.push(hoge2 + hoge3)
        console.log(hoge)
        console.log(hoge2)
        this.$store.commit('setDB', hoge)
        this.db = hoge
        console.log(this.$store.state.db)
    });
});
    }
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hello{
    text-align:center;
  }
  h1,
  h2 {
    font-weight: normal;
  }
  a {
    color: #42b983;
  }
    .hiduke{
    width:30vw;
    height:10vw;
    border-radius:3rem;
    display: flex;
            cursor : pointer;
    justify-content: center;
align-items: center;
    color:white;
background: gray;
margin:2vw 1vw;
  }
  .error{
    color:red;
  }
  .yotei{
    margin:auto;
  }
</style>
