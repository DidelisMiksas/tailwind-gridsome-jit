<template>
  <Layout>
    <intro :title="intro.title" :text="intro.text" />
  </Layout>
</template>

<page-query>
  query {
    frontPage: allWordPressPage(
      filter: { template: { eq: "template-front-page.php" } }
    ) {
      edges {
        node {
          template
          acf {
            intro {
              title
              text
            }
          }
        }
      }
    }
  }
</page-query>

<script>

  import Intro from '@/components/Intro.vue';

  export default {
    data() {
      return {
        intro: {
          title: null,
          text: null
        }
      }
    },
    components: {
      Intro
    },
    created () {
      const intro = this.$page.frontPage.edges[0].node.acf.intro;
      this.intro.title = intro.title
      this.intro.text = intro.text
    },
  }
</script>

<style>

</style>
