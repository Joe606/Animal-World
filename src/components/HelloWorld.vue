<template>
  <div id='container'>
    <swiper  ref="mySwiper" :options="swiperOptions" >
      <swiper-slide v-for="item in items" :key="item">
        <a href="item.value">
        <img alt="none" :src="item.value" width="1100" height="450">
       <div class="anota">{{item.name}}</div>
       <div class='detail'>{{item.detail}}</div>
        </a>
        
      </swiper-slide>
      
      <div class="swiper-pagination" slot="pagination">
        
         
      </div>
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/swiper-bundle.css";
export default {
  name: "HelloWorld",
  components: {
    Swiper,
    SwiperSlide,
  },

  data() {
    return {
      items:[
        {name:'cheatah',
        value:require('@/assets/cheatah.jpg'),
        detail:' a large cat native to Africa and central Iran. \
              the fastest land animal, capable of running at 80 to 128 km/h.'},
        {name:'owl',value:require('@/assets/owl.jpg'),detail:'an upright stance, a large, broad head, binocular vision, binaural hearing, sharp talons, and feathers adapted for silent flight.'},
        {name:'panda',value:require('@/assets/panda.jpg'),detail:'a bear native to south central China. large, black patches around its eyes, over the ears, and across its round body.'},
        {name:'tiger',value:require('@/assets/tiger.jpg'),detail:'the largest extant cat species and a member of the genus Panthera. It is an apex predator, primarily preying on ungulates such as deer and wild boar. '},
        {name:'wolf',value:require('@/assets/wolf.jpg'),detail:'a large canine native to Eurasia and North America. The wolf is the largest extant member of Canidae, males averaging 40 kg and females 37 kg.'},

      ],
      swiperOptions: {
        pagination: {
          el: ".swiper-pagination",
          type: "bullets",
          clickable: true,
          bulletElement : 'li',
        },

        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },

        width: window.innerWidth,
        // height: 400,
        

        grabCursor: true,
        loop: true,
        
        autoplay: {
          delay: 3000,
          stopOnLastSlide: false,
          disableOnInteraction: true,
        },
        freeMode: true,
        
        
      },
    };
  },

  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper;
    },
  },
  mounted() {
    console.log("Current Swiper instance object", this.swiper);
    //this.swiper.slideTo(3, 1000, false);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#container {
  /*
  margin: 0px;
  border: 0px;
  padding: 0px;
  width: 100%;
  height: 400px;

  text-align: center;

  color: blue;
  font-family: "Times New Roman", Times, serif;
  font-size: 300px;
  background-color: rgb(232, 240, 220);
  --swiper-pagination-color: #f30d0d;
  
 width: 100%;
 text-align: center;
 font-size: 300px;
 */

 /* background: #fff; */
 display: -webkit-box;
 display: -ms-flexbox;
 display: -webkit-flex;
 display: flex;
 -webkit-box-pack: center;
 -ms-flex-pack: center;
 -webkit-justify-content: center;
 justify-content: center;
 -webkit-box-align: center;
 -ms-flex-align: center;
 -webkit-align-items: center;
 align-items: center;
 transition: 300ms;
}
.anota{
  position: relative;
  right: 80px;
  top:-40px;
  z-index: 3;
  font-size: 30px;
  font-family: 'Times New Roman', Times, serif;
  color: rgb(99, 99, 122);
}
.detail{
  position: relative;
  left: 850px;
  top:-190px;
  z-index: 2;

  font-size: 20px;
  font-family: 'Times New Roman', Times, serif;
  color: rgb(249, 250, 249);
  width: 300px;

}
a{
  text-decoration: none;
}

</style>
