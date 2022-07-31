<template>

<!-- wanna bullet ? change pagination "type" -->
  <swiper
    :modules="modules"
    :slides-per-view="1"
    :space-between="50"
    :autoplay="{delay:2500}"
    navigation

    
    :pagination="{ clickable: true, dynamicBullets: true, type: custom }"
    
    :scrollbar="{ draggable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide v-for="(color,index) in colors" :key="index">
      <div class="swiper-card"  
      :style="{'background': color}">


      </div>
     
    </swiper-slide>
    
  </swiper>
</template>
<script>
  // import Swiper core and required modules
  import { Navigation, Pagination, Scrollbar, Autoplay, A11y } from 'swiper';

  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';
  import 'swiper/css/navigation';
  import 'swiper/css/pagination';
  import 'swiper/css/scrollbar';
  import 'swiper/css/bundle';
  import 'swiper/css/autoplay'

  // Import Swiper styles
  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const colors=['red','orange','blue']

      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
        modules: [Navigation, Pagination, Autoplay, Scrollbar, A11y],
        colors
      };
    },
  };
</script>

<style lang="css">

.swiper-card{
  width: 300px;
  height: 300px;
}
  
</style>