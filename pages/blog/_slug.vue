<template>
  <div>
    <h1>{{ post.title }}</h1>
    <p>{{ post.text }}</p>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import gql from 'graphql-tag'

const POST_QUERY = gql`query
Post($slug: String!): {
  post(filter: { slug: {
    eq: $slug
  } }) {
    title
    body
  }
}`

@Component({})
export default class Slug extends Vue {}
</script>
