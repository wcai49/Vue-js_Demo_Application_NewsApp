<template>
<div>
  <div class="header"></div>

  <div class="content">
  <ul>
    <li v-for="(item, index) in pageLists"
        :key="index">

        {{item.title}}
<p></p>
        -{{item.content}}
      <p></p>
    </li>
  </ul>
  </div>
</div>
</template>

<script>
  import store from '@/store'
    export default {
        name: "List",
      store,
      computed: {
        pageLists() {
          return store.state.lists
        }
      }
  }
</script>

<style scoped lang="scss">
  .header{
    position: fixed;
    width: 100%;
    height: 40px;
    line-height: 60px;
    display: flex;
    background-color: #42b983;
    flex-flow: row nowrap;
    justify-content: space-around;

  }
  .content{
    position: fixed;
    top: 40px;
    width: 100%;
    height: 711px;
    background-color: lightgray;
  }

</style>
