<template>
  <header class="pt-[40px] absolute left-0 top-0 w-full bg-gray-100">
    <div class="container flex items-center justify-between">
      <img :src="logo.dark" alt="VSBL Studio Logo.">
    </div>
  </header>
</template>

<static-query>
  query {
  headerOptions: 
    allAcfOptions {
      edges {
        node {
          acf {
            header_options {
              header_logo_white {
                url
              }
              header_logo_dark {
                url
              }
            }
          }
        }
      }
    }
  }
</static-query>

<script>
export default {
  data() {
    return {
      logo: {
        white: null,
        dark: null
      }
    }
  },
  created () {
    const headerOptions = this.$static.headerOptions.edges[0].node.acf.header_options
    this.logo.white = headerOptions.header_logo_white.url;
    this.logo.dark = headerOptions.header_logo_dark.url;
  },
}
</script>

<style>

</style>