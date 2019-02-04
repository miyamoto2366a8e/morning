<template>
  <div class="hello animated fadeIn">
    <h1>{{this.$store.state.weatherName}}の天気</h1>
    <!-- <h2>最低気温：{{this.weather[0]["main"]["temp_min"]}}。最高気温:{{this.weather[0]["main"]["temp_max"]}}</h2> -->
    <table>
    <tr>
    <th>日時</th><th>天気</th><th></th><th>気温</th>
    </tr>
    <tr>
    <th>{{this.weather[0]["dt_txt"]}}</th><th>{{this.weather[0]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[0]["weather"][0]["icon"] + ".png"'></th>
    <th>{{this.weather[0]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[1]["dt_txt"]}}</th><th>{{this.weather[1]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[1]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[1]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[2]["dt_txt"]}}</th><th>{{this.weather[2]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[2]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[2]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[3]["dt_txt"]}}</th><th>{{this.weather[3]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[3]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[3]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[4]["dt_txt"]}}</th><th>{{this.weather[4]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[4]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[4]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[5]["dt_txt"]}}</th><th>{{this.weather[5]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[5]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[5]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[6]["dt_txt"]}}</th><th>{{this.weather[6]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[6]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[6]["main"]["temp"]}}</th>
    </tr>
    <tr>
    <th>{{this.weather[7]["dt_txt"]}}</th><th>{{this.weather[7]["weather"][0]["main"]}}</th>
    <th><img :src='"../assets/" + this.weather[7]["weather"][0]["icon"] + ".png"'></th>
        <th>{{this.weather[7]["main"]["temp"]}}</th>
    </tr>
    </table>
    <!-- {{this.weather[1]["dt_txt"]}}{{this.weather[1]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[1]["weather"][0]["icon"] + ".png"'>
    {{this.weather[2]["dt_txt"]}}{{this.weather[2]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[2]["weather"][0]["icon"] + ".png"'>
    {{this.weather[3]["dt_txt"]}}{{this.weather[3]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[3]["weather"][0]["icon"] + ".png"'>
    {{this.weather[4]["dt_txt"]}}{{this.weather[4]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[4]["weather"][0]["icon"] + ".png"'>
    {{this.weather[5]["dt_txt"]}}{{this.weather[5]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[5]["weather"][0]["icon"] + ".png"'>
    {{this.weather[6]["dt_txt"]}}{{this.weather[6]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[6]["weather"][0]["icon"] + ".png"'>
    {{this.weather[7]["dt_txt"]}}{{this.weather[7]["weather"][0]["main"]}}
    <th><img :src='"../assets/" + this.weather[7]["weather"][0]["icon"] + ".png"'> -->
  </div>
</template>

<script>
import axios from 'axios'
  export default {
    name: 'weather',
    data() {
      return {
        myset: "",
        myset_name: "test",
        tien:[],
        news:[],
        date:"",
        date2:"",
        weather:[],
        weatherflag:{
          // 雪か雨
          all:false,
          rain:false,
          snow:false
        }
      }
    },
  created() {
    // 都市データをURLに組み込む。
    var url = "https://api.openweathermap.org/data/2.5/forecast?id=" + this.$store.state.weather + "&units=metric&APPID=0a8f60c07e0ec92c23a485ee7f9f4c94"
   axios.get(url)
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
     console.log(aaa)
    //  天気フラグ操作
     if(response.data.list[0]["weather"]["0"]["main"] == "snow"){
       this.weatherflag["snow"] = true
       this.weatherflag["all"] = true
     }
   }.bind(this))
   .catch(function(error){
     console.log(error)
   })
   switch( this.$store.state.weather ) {
    case '1850147':
        console.log('東京');
        break;
    case '1853904':
        console.log('大阪');
        break;
    case '2112669':
        console.log('茨城');
        break;
}
  },
methods: {
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  p{
    font-size:16px;
  }
</style>
