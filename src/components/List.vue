<template>
  <div class="list">
    <div class="container">
      <div class="row">
        <h1>{{title}}</h1>
        <div v-for="r in rows" :key="r.id" class="item" >

          <router-link :to="'c/' + r.object.id " v-if="r.object">
            <p><strong>{{r.title}}</strong></p>
            <p>{{r.description}}</p>
          </router-link>
          <router-link :to="'c/' + r.id " v-else>
            <p><strong>{{r.title}}</strong></p>
            <p>{{r.description}}</p>
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'list',
  data () {
    return {
      title: '列表',
      content: 'content',
      rows: {},
      loading: true
    }
  },
  created: function(){
    let listApi = "https://api.segmentfault.com/news/newest"
    this.$http.get(listApi).then( res => {
      this.rows = res.data.data.rows
      this.loading  = false
      console.log(this.rows[0].object.id);
    })
  }
}
</script>

<style>
  .item {
    text-align: left;
    border-bottom: 1px solid #ddd;
    margin-bottom: 20px;
    cursor: pointer;
  }
  a:hover{
    text-decoration: none;
  }
</style>
