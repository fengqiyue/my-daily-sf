<template>
  <div class="list">
    <div class="container">
      <div class="row">
        {{title}}
        {{ $route.params.id }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'detail',
  data () {
    return {
      title: '标题!',
    }
  },
  created: function(){
    let listApi = "https://api.segmentfault.com/article" + ""
    this.$http.get(listApi).then( res => {
      console.log('res',res)
    })
  }
}
</script>
