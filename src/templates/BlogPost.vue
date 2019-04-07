<template lang="html">
  <Layout>
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
  }
}
</page-query>

<script>
export default {};
</script>
