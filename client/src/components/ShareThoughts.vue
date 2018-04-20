<script>
import MicroPostsService from '../MicroPostsService'

export default {
  name: 'ShareThoughts',
  data () {
    return {
      text: ''
    }
  },
  methods: {
    async shareThouths () {
      await MicroPostsService.insertMicroPost(this.text)
      this.$router.push('/')
    }
  }
}
</script>

<template>
<div class="share-thoughts">
  <label for="share-thoughts">What do you want to share?</label>
  <input id="share-thoughts" v-model="text" placeholder="Be nice!"/>
  <button v-on:click="shareThouths">Share!</button>
</div>
</template>

<style scoped>
</style>
