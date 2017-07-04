<template>
  <div class="detail">
    <div class="container">
      <div class="row">
        <h1 class="title">{{ title }}</h1>
        <hr>
        <article>
          {{content}}
        </article>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'detail',
  data () {
    return {
      title: 'title',
      content: 'content'
    }
  }
}
</script>
