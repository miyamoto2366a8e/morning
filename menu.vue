<template>
  <div class="main animated fadeIn">
    <br>
<router-link to="/" class="home"><h1>HOME</h1></router-link>
<router-link to="/todo" class="todo"><h1>予定入力</h1></router-link>
<router-link to="/conf" class="conf"><h1>設定</h1></router-link>
<div class="sign" @click="signIn" v-if="this.$store.state.signflag == 0">ログイン</div>
<div class="sign" @click="signOut" v-if="this.$store.state.signflag == 1">ログアウト</div>
  </div>

</template>

<script>
import firebase from 'firebase'
export default {
  name: 'sign',
  data () {
    return {
    // email:"",
    // password:"",
    // password2:"",
    // check:0,
    test:null
    }
  },
  created() {

  },
methods: {
  signIn() {
    firebase.auth().setPersistence(firebase.auth.Auth.Persistence.LOCAL)
.then(() => {
          const provider = new firebase.auth.GoogleAuthProvider()
        firebase.auth().signInWithPopup(provider)
                      firebase.auth().onAuthStateChanged(user => {
            // ログイン状態ならuserが取得できる
            this.user = user ? user : {}
            console.log(this.user)
            if(this.user['uid'] != null){
              this.$store.commit('setuid', this.user['uid']),
              this.$store.commit('setSignflag', 1)
              this.$router.push('/')
              }
            //   this.hello = "ようこそ" + this.user['email'] + "さん"
            //   this.$store.commit('setmyset', db.collection('test').doc(this.user.uid))
          })
})
  //   onchange () {
  //     (this.password == this.password2)? this.check =  1: alert("パスワードが間違っています")
  // },
  // test(){
  //   console.log("test")
  //     this.$store.commit('setuid', this.user['user']['uid'])
  //   this.$router.push('HelloWorldB')
  // },
  // kanryo () {
  //     firebase.auth().signInWithEmailAndPassword(this.email, this.password).then(
  //       user => {
  //         alert('ログインしました')
  //           this.user = user ? user : {}
  // // this.$router.push('HelloWorldB')
  // window.setTimeout( this.test, 2000 );
  //         // this.user = user ? user : {}
  //       },
  //       err => {
  //         alert(err.message)
  //       },
  //     )
  // },
},
      signOut() {
              firebase.auth().signOut()
              this.$store.commit('setuid', null),
              this.$store.commit('setSignflag', 0)
              alert("ログアウトしました")
      },
}
}
</script>

<style scoped>
.main{
  text-align:center;
}
  .sign{

        cursor : pointer;
        border-radius:3rem;
        display: flex;
    justify-content: center;
align-items: center;
    color:white;
background: #0099CC;
margin:2vw 1vw;
width:98%;
height:100px;
font-size:50px;
  }
  .home{
    margin:8vw;
    text-decoration: none;
    color:black;
  }
  .todo{
    margin:8vw;
    text-decoration: none;
    color:black;
  }
  .conf{
    margin:8vw;
    text-decoration: none;
    color:black;
  }
</style>
