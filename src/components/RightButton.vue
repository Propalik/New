<template>
    <div class="btn2" @click="showList">
      <p>По умолчанию</p>
      <img src="@/assets/img/Icon 2.svg" />
      <ul v-if="statusShow">
        <li v-for="(item, index) in list" :key="index" @click="select(item)">{{ item }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        list: ["Сначала доступные", "Сначала дорогие"],
        statusShow: false,
      };
    },
    methods: {
      showList() {
        this.statusShow = !this.statusShow;
      },
      select(event, el) {
          event.stopPropagation()
        this.$emit('select', el);
      },
    },
    emits: ['select'],
  };
  </script>
  
  <style lang="scss" scoped>
  .btn2 {
      position: absolute;
    background: #ffffff;
    padding: 8px 16px;
    left: 1582px;
    
    p {
      margin-right: 13px;
    }
    ul {
      position: absolute;
      flex-direction: column;
      padding: 6px;
      top: 100%;
      left: 0;
      width: 230px;
      background: #ffffff;
  
      box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.08);
      border-radius: 8px;
    }
  }
  </style>
  