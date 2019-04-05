<template lang="html">
  <div>
    <h3>Latest Post</h3>
    <article v-for="edge in $static.allBlogPost.edges" :key="edge.id">
      <h4>{{ edge.node.title }}</h4>
      <p>{{ edge.node.date }}</p>
      <g-link :to="`/posts/${edge.node.slug}`">Read More</g-link>
    </article>
  </div>
</template>

<static-query>
  query PostLatest {
  allBlogPost {
    edges {
      node {
        id
        content
        excerpt
        title
        tags
        date (format: "MMM Do YYYY")
        slug
      }
    }
  }
}

</static-query>
