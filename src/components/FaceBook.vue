<template>
  <div class="facebook">
    <div class="facebook__left">
      <div class="input">
  <input class="email" placeholder="Email address or phone number"/>
      </div>
      <div class="input">
   <input class="password" placeholder="Password"/>
      </div>
      <div class="button">
      <button>Log In</button>
      </div>
      <div class="forgot">
        Forgotten password?
      </div>
      <div class="create-account">
        <button>
        Create New Account
        </button>
      </div>
    </div>
     <div class="facebook__right">
       <div class="facebook__right__upper"><img src="https://static.xx.fbcdn.net/rsrc.php/y8/r/dF5SId3UHWd.svg"/></div>
       <div class="facebook__right__lower">{{text}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FaceBook',
  data(){
    return {
      text:{}
    }
  },
  methods:{
    getData() {
      let req= new XMLHttpRequest()
      let url="https://jsonplaceholder.typicode.com/posts/1"
      req.open("GET",url)
      req.send()
      req.onreadystatechange=()=>{
      this.text=JSON.parse(req.responseText).body
      }
    }
  },
  mounted(){
    this.getData()
  }
}
</script>

<style scoped lang="scss">
@import '@/mixins/responsive';
.facebook{
  width:100vw;
  height:100vh;
  padding:20px;
  display:flex;
  padding-top:106px;
  &__left {
    height:394px;
    width:396px;
    background-color:white;
    border-radius:8px;
    padding:20px;
    .input {
      width:358px;
      .email{
        margin-bottom:8px;
      }
    input{
      width:100%;
      padding:14px;
      border: 1px solid #dddfe2;
      border-radius: 4px;
      font-size: 17px;
    }
    }
    .button {
      margin-top:8px;
      button{
        background-color: #1877f2;
        border-radius: 6px;
        color:white;
        padding: 20px;
        width:100%;
        font-size: 16px;
        border:none;
        font-weight: bold;
      }
    }
    .forgot{
          color: #1877f2;
    font-size: 14px;
    font-weight: 500;
    margin-top:16px;
    border-bottom: 1px solid #dadde1;
    padding-bottom: 40px;
    }
    .create-account {
      margin-top:6px;
     button {
       color:white;
      background-color: #42b72a;
      border:none;
      border-radius: 6px;
      padding:16px;
      font-size: 20px;
      font-weight: bold;
     }
    }
  }
  &__right{
        text-align: left;
    margin-left: 45px;
    width: 700px;
    &__upper{
     width: 280px;
    }
  }
}
</style>
