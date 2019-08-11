<template>
  <Layout>
    <div class="article">
      <h1>{{ $page.bibleVerse.title }}</h1>
      <span>{{ $page.bibleVerse.date }}</span>
      <g-image :src="$page.bibleVerse.image"/>
      <div class="content" v-html="$page.bibleVerse.content" />
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo () {
    return {
      title: this.$page.bibleVerse.title
    }
  }
}
</script>

<page-query>
  query BibleVerse ($path: String!) {
    bibleVerse (path: $path) {
      title
      date (format: "D MMMM, YYYY")
      content
      image
    }
  }
</page-query>

<style>

</style>
