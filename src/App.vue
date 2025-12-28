<template>
  <div class="container">
    <div class="items">
      <BaseNotification
        v-for="(notification, index) in notifications"
        :key="index"
        :title="notification.title"
        :text="notification.text"
        :type="notification.type"
        :isActive="notification.isActive"
        @clickOnNotification="notifications[index].isActive = false"
      />
    </div>
    <button
      @click="addNotification"
    >Добавить новое уведомление</button>
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
            type: 'danger',
            isActive: true
          },
          {
            title: 'Need Attention',
            text: 'Adipiscing elit, sed do eiusmod',
            type: 'warning',
            isActive: false
          },
          {
            title: 'Success',
            text: 'consectetur adipiscing elit sed',
            type: 'success',
            isActive: true
          },
          {
            title: 'Other Condition',
            text: 'consectetur adipiscing elit sed',
            type: 'info',
            isActive: true
          }
        ]
      }
    },
    methods: {
      addNotification() {
        this.notifications.push({
          title: 'Hello World',
          text: "Hello Hello",
          type: "success",
          isActive: true
        });
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
