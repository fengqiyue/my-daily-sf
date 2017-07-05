<template>
  <div class="contain">
    <div class="container">
      <div class="row">
        <h2>{{content.title}}</h2>
        <article  v-html="content.parsedText" v-if="content.parsedText"></article>
        <article  v-html="content.readParsedText" v-else ></article>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'contain',
  data () {
    return {
      title: '标题!',
      id: this.$route.params.id,
      content: {}
    }
  },
  created: function(){
    let contentApi
    if(this.id.slice(0,3) == '119'){
      contentApi = `https://api.segmentfault.com/article/${this.id}`
    } else if(this.id.slice(0,3) == '121'){
      contentApi = `https://api.segmentfault.com/news/${this.id}`
    }


    this.$http.get(contentApi).then( res => {
      this.content = res.data.data
    })
  }
}
</script>
