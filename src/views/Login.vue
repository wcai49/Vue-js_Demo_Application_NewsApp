<template>
  <div>


    <div class="header">

      <div class="headerTitle">VUE.JS新闻</div>

    </div>

    <div class="content">


    <form action="" v-if="!isReg">
      <div class="contentMain">
    用户名:
    <p></p>
    <input type="text" v-model="name">
    <p></p>
    密  码:
    <p></p>
    <input type="password" v-model="password">
    <p></p>
    <button type="button" @click="login()">登录</button>
    <button type="button" @click="reg()">注册</button>
      </div>
    </form>

    <form v-else>
      <div class="contentMain">
      用户名:
        <p></p>
      <input type="text" v-model="name">
      <p></p>
      密码
        <p></p>
      <input type="password" v-model="password">
      <p></p>
      再次输入密码
        <p></p>
      <input type="password" v-model="repeat">
      <p></p>
      <button type="button" @click="addUser()">确定</button>
      <button type="button" @click="cancel()">取消</button>
      </div>
    </form>


    </div>

  <div class="footer">

  </div>
  </div>
</template>

<script>
    export default {
        name: "Login",
      data () {
          return {
              isReg : false,
              name: '',
              password: '',
              repeat: ''
          }
      },
      methods:{
          login () {
            if(localStorage.getItem("name")===this.name && localStorage.getItem("password")===this.password) {
              this.name = ''
              this.password = ''
              this.$router.push('/home/list')
            }
            else
              alert("用户名密码不正确")
            },
          reg () {
            this.isReg = true
        },
          addUser () {
            if (this.password === this.repeat) {
              localStorage.setItem("name", this.name)
              localStorage.setItem("password", this.password)
              this.name = ''
              this.password= ''
              this.isReg = false
            }
            else
              alert ("两次密码输入需要一致")

          },
          cancel () {
            this.isReg = false
          }
      }
    }
</script>

<style scoped lang="scss">
  .header{
    position: fixed;
    width: 100%;
    height: 60px;
    line-height: 60px;
    display: flex;
    background-color: #42b983;
    flex-flow: row nowrap;
    justify-content: space-around;

  }
  .headerTitle {
    font-size: 40px;
    flex: 1;
    text-align: center;
    border-top: 1px solid #fff;
    font-style: initial;
    color: #fff;
  }
  .footer{
    position: fixed;
    width: 100%;
    height: 40px;
    line-height: 60px;
    left: 0;
    bottom: 0;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-around;
    background-color: #42b983;

  }
  .content{
    position: fixed;
    width: 100%;
    height: 712px;
    top: 60px;
    background-color: lightgray;
  }
  .contentMain{
    position: fixed;
    width: 100%;
    top: 140px;
    left: 100px;
  }


</style>
