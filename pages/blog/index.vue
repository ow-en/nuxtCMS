<template>
  <div>
    <ul>
      <li
        v-for="(post, index) in allPosts"
        :key="index"
      >
        <h2>
          <nuxt-link :to="`/blog/${post.slug}`">
            {{ post.title }}
          </nuxt-link>
        </h2>
        <p>{{ post.text }}</p>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import gql from 'graphql-tag'

const POSTS_QUERY = gql`
allPosts(type: $any): {
  title
  body
  slug
}
`

@Component({})
export default class IndexBlog extends Vue {}
</script>
