<template>
    <div id="app" class="app-container">
      <header class="header">
        <h1>My Vue App</h1>
        <div class="notification-wrapper">
          <button @click="toggleNotifications" class="notification-button">
            <span v-if="notifications.length > 0" class="notification-badge">{{ notifications.length }}</span>
            <svg xmlns="http://www.w3.org/2000/svg" class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M18 8a6 6 0 0 0-12 0c0 7-3 9-3 9h18s-3-2-3-9" />
              <path d="M13.73 21a2 2 0 0 1-3.46 0" />
            </svg>
          </button>
          <div v-if="showNotifications" class="notification-dropdown">
            <ul>
              <li v-for="(notification, index) in notifications" :key="index">{{ notification }}</li>
              <li v-if="notifications.length === 0">No new notifications</li>
            </ul>
          </div>
        </div>
      </header>
      <main class="content">
        <p>Welcome to your Vue.js app!</p>
      </main>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        notifications: ["New message received", "System update available", "Weekly report ready"], // Sample data
        showNotifications: false,
      };
    },
    methods: {
      toggleNotifications() {
        this.showNotifications = !this.showNotifications;
      },
    },
  };
  </script>
  
  <style scoped>
  .app-container {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }
  
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    background-color: #4caf50;
    color: white;
  }
  
  .notification-wrapper {
    position: relative;
  }
  
  .notification-button {
    background-color: #fff;
    border: none;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    position: relative;
  }
  
  .notification-badge {
    background-color: #f44336;
    color: white;
    border-radius: 50%;
    padding: 2px 6px;
    font-size: 12px;
    position: absolute;
    top: 0;
    right: 0;
    transform: translate(50%, -50%);
  }
  
  .icon {
    width: 20px;
    height: 20px;
    stroke: #4caf50;
  }
  
  .notification-dropdown {
    position: absolute;
    top: 50px;
    right: 0;
    background: white;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    overflow: hidden;
    z-index: 10;
    width: 200px;
  }
  
  .notification-dropdown ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  .notification-dropdown li {
    padding: 10px;
    border-bottom: 1px solid #ddd;
  }
  
  .notification-dropdown li:last-child {
    border-bottom: none;
  }
  
  .content {
    padding: 20px;
  }
  </style>
  