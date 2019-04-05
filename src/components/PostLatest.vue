<template lang="html">
  <div>
    <h3>Latest Post</h3>
    <article v-for="edge in $static.allBlogPost.edges" :key="edge.id">
      <!-- <h4>Post Title</h4>
      <p>Here is some fake test for a post body summary</p>
      <a href="#">Link</a> -->
      <div v-html="edge.node.content"></div>
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
      }
    }
  }
}

</static-query>
