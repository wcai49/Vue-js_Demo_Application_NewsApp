<template>
<div>

  <div class="header">
    新闻发表
  </div>

  <div class="contents">
  <div class="contentsMain">
  <p>标题</p>
  <input type="text" v-model="title">
  <p>内容</p>
  <input type="text" v-model="content">
  <p></p>
  <button class="btn" @click="add()">添加</button>
  </div>
  </div>
</div>
</template>

<script>
  import store from '@/store'
    export default {
        name: "Add",
      store,
      data () {
          return {
            title: '',
            content: ''
          }
      },
      methods: {
          add () {
            store.commit('addItem', {
              title: this.title,
              content: this.content
            })
            this.title = ''
            this.content =''
            this.$router.push('./home/list')

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
    color: #fff;


  }
  .contents{
    position: fixed;
    top: 50px;
    left: 0;
    height: 704px;
    width: 100%;
    background-color: lightgray;
  }
  .contentsMain{
    position: fixed;
    top: 100px;
    left: 80px;
  }

</style>
