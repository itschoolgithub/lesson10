<template>
  <div class="container">
    <div class="items">
      <BaseNotification
        v-for="(notification, index) in notifications"
        :key="index"
        :title="notification.title"
        :text="notification.text"
        :type="notification.type"
      />
    </div>
  </div>
</template>

<script>
  import BaseNotification from '@/components/BaseNotification.vue';

  export default {
    name: "App",
    components: {
      BaseNotification
    },
    data() {
      return {
        notifications: [
          {
            title: 'Someting wrong',
            text: 'Lorem ipsum dolor sit amet',
            type: 'danger'
          },
          {
            title: 'Need Attention',
            text: 'Adipiscing elit, sed do eiusmod',
            type: 'warning'
          },
          {
            title: 'Success',
            text: 'consectetur adipiscing elit sed',
            type: 'success'
          },
          {
            title: 'Other Condition',
            text: 'consectetur adipiscing elit sed',
            type: 'info'
          }
        ]
      }
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
