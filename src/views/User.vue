<template>
  <div>

  <div class="header">

    <div class="headerTitle">个人中心</div>

  </div>

  <div class="content">
    <button class="editButton" @click="add()" ><strong>编辑新闻</strong></button>'
    <button class="quitButton" @click="quit()"> <strong> 退出登录</strong></button>
  </div>

  </div>
</template>

<script>
    export default {
        name: "User",
      methods: {
          add () {
            this.$router.push('../add')
          },
          quit () {
            this.$router.push('../')
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
  .headerTitle{
    font-size: 20px;
    flex: 1;
    text-align: center;
    border-top: 1px solid #fff;
    font-style: initial;
    color: #fff;

  }
  .content{
    position: fixed;
    top: 50px;
    left: 0;
    height: 704px;
    width: 100%;
    background-color: lightgray;
  }
  .editButton{
    position: fixed;
    top: 120px;
    left:40px;
    width: 300px;
    font-size: 30px;
    background-color: deepskyblue;
  }
  .quitButton{
    position: fixed;
    width: 250px;
    bottom: 120px;
    left: 60px;
    font-size: 30px;
    background-color: red;
    color: #fff;

  }







</style>
