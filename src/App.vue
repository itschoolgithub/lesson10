<template>
  <div class="container">
    <div class="items">
      <BaseNotification />
    </div>
  </div>
</template>


<script>
  import BaseNotification from '@/components/BaseNotification.vue';

  export default {
    name: "App",
    components: {
      BaseNotification
    }
  }
</script>

<style>
  .container {
    width: calc(100% - 60px);
    max-width: 1280px;
    margin: 0 auto;
    padding-block: 60px;
  }

  .items {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
</style>
