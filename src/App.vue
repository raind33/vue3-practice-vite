<template>
  <div>
    <vote :title="'vue好学号'"/>
  </div>
</template>

<script>
import Vote from './components/Vote.vue'

export default {
  name: 'App',
  components: {
    Vote
  }
}
</script>
