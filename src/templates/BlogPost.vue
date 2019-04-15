<template lang="html">
  <Layout :background="$page.blogPost.image">
    <h1>{{ $page.blogPost.title }}</h1>
    <p>{{ $page.blogPost.date }}</p>
    <div v-html="$page.blogPost.content"></div>
  </Layout>
</template>

<page-query>
  query Post ($path: String!){
  blogPost (path: $path){
    title
    content
    tags
    date (format: "MMM Do YYYY")
    image (height: 400)
  }
}
</page-query>

<script>
export default {};
</script>
