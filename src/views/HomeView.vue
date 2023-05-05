<template>
  <div class="main-container">
    <BaseButton @select="select"/>
    <RightButton @select="select"/>
  
  
</div>
</template>

<script>
import Container from '@/components/Container.vue';
import BaseButton from '@/components/BaseButton.vue';
import RightButton from '@/components/RightButton.vue';
export default {
  components: { BaseButton, RightButton, Container },
  name: 'HomeView',
  comments:{
    Container,
    BaseButton,
    RightButton
  },
  data() {
  },
  methods:{
    select(el){
      console.log(el, 'vvv')
    }
  }
}
</script>

<style lang="scss" scoped>
.main-container{
  margin-top: 40px;
}

</style>
