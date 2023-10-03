<template>
     <div style="margin-bottom: 50px;">
    <b-carousel
    ref="myCarousel1"
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="transparent"
      color="#ccc"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
    <b-carousel-slide v-for="slide in slides">
      <template #img>
          <router-link :to="{path:'/event',query:{id: slide.id}}" class="slide__link">
          <img style="display: flex;margin: auto; border: 1px solid transparent; border-radius: 10px 10px;"
            class="d-block img-fluid w-100"
            :src="slide.img"
            alt="image slot"
            >
          </router-link>
          </template>
      </b-carousel-slide>
</b-carousel>
</div>
</template>
<script>
export default {
    props:['slides'],
    data() {
      return {
        slide: this.startSlide(),
        sliding: null
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      },
      prev() {
        this.$refs.myCarousel1.prev()
      },
      next() {
        this.$refs.myCarousel1.next()
      },
      startSlide() {
      return parseInt(this.slides.length/2);
  }, 
    }
}
</script>
<style>
#carousel-1{
  position: relative;
}
.carousel-inner{
  width: 100% !important;
  margin: auto !important;
  overflow: hidden !important;
  display: flex !important;
}
.carousel{
    display:flex;
    justify-content:center;
}
.carousel-item{
  display: block !important;
  margin:0 !important;
  opacity: 0.5 !important;
  transition: all ease-out 0.1s !important;
}
.carousel-item.active{
  opacity: 1 !important;
}
.slide__link{
  margin: auto;
  display: block;
  width: 100% !important;
}
.slide__link img{
  border-radius: 0px !important;
  width: 100% !important;
}

.carousel-control-prev,.carousel-control-next {
  width: 40px !important;
  height: 100px !important;
  align-items: center;
  margin: auto;
  border-radius: 2px 2px;
  z-index: 0 !important;
}
.carousel-control-prev{
  left: 10px !important;
  z-index: 0!important;
  background-color:#ead5cc !important;
  transition: 0.3s !important;
  opacity: 0.5 !important;
}
.carousel-control-next{
  right: 10px !important;
  z-index: 0!important;
  background-color: #ead5cc !important;
  transition: 0.3s !important;
  opacity: 0.5 !important;
}
.carousel-control-prev:hover,
.carousel-control-next:hover{
  opacity: 0.8 !important ;
}
.carousel-indicators{
  bottom: -60px !important;
}
.carousel-indicators li{
  background-color: #ead5cc !important;
  width: 10px !important;
  height: 10px !important;
  margin: 0 5px !important;
  border-radius:50% !important;
}
</style>