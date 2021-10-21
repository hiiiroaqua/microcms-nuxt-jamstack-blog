<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://blogtutorial.microcms.io/api/v1/blog',
      {
        headers: {'X-API-KEY': '9309ffc8-f4c3-4c73-95a4-4a8deef642a7'}
      }
    )
    return data
  }
}
</script>