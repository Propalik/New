<template>
  <div class="btn" @click="showList">
    <img src="@/assets/img/Icon.svg" />
    <p>Фильтры</p>
    <ul v-if="statusShow">
      <li v-for="(item, index) in list" :key="index" @click="select(item)">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: ["Aкне студия", "АМИ Париж", "Вквадрате2", "Каменный остров"],
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
.btn {
    position: relative;
  background: #ffffff;
  padding: 8px 16px;
  margin: 0 160px;
  left: 0;

  img {
    margin-right: 10.5px;
  }
  ul {
    position: absolute;
    flex-direction: column;
    padding: 6px;
    top: 100%;
    left: 0;
    width: 320px;
    background: #ffffff;

    box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.08);
    border-radius: 8px;
  }
}
</style>
