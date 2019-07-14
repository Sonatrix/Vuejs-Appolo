<template>
   <q-page class="flex flex-center">
    <q-list highlight >
      <q-list-header>Task</q-list-header>
      <q-item tag="label" v-for="i in articles" :key="i.id">
        <q-item-main>
          <q-item-tile label>{{i.title}}</q-item-tile>
          <q-item-tile sublabel>{{i.published_at}}</q-item-tile>
        </q-item-main>
      </q-item>
    </q-list>
  </q-page>
</template>

<style>
</style>

<script>
import gql from 'graphql-tag'
const ArticlesQuery = gql`
  query {
    articles {
      title
      published_at
      title
    }
  }
`

export default {
  name: 'PageIndex',
  data () {
    return {
      // Initialize your apollo data
      articles: []
    }
  },
  apollo: {
    // Simple query that will update the 'hello' vue property
    articles: ArticlesQuery
  }
}
</script>
