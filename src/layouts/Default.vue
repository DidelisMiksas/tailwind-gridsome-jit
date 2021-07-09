<template>
  <div>
    <Header />
    <main class="pt-40">
      <div class="container">
        <slot></slot>
      </div>
    </main>
  </div>
</template>

<static-query>
</static-query>

<script>
  import Header from '@/components/Header.vue';

  export default {
    components: {
      Header
    }
  }

</script>

<style>

</style>
