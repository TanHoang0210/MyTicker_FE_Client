<template>
    <main class="main">
        <div class="main__container">
            <div class="home__container">
                <slide-show :slides="categories"></slide-show>
                <categories :categories="categories"></categories>
            </div>
        </div>
    </main>
</template>
<script>
import Categories from "@/components/Home/MainComponent/Categories.vue"
import SlideShow from "@/components/Home/MainComponent/SlideShow.vue"
export default{
    components:{SlideShow,Categories},
    name:'HomeMain',
    data() {
    return{
    categories: [{
      id: 1,
      img: 'https://i.ibb.co/qRH5qQC/slide2.jpg',
      name: 'Con Hẻm Xíu Xiu - Đêm nhạc gây quỹ cho chương trình "Như chưa hề có cuộc chia ly"',
      date:'22/10/2023',
      type:'Theater'
      }, {
      id: 2,
      img: 'https://i.ibb.co/X5h4D5d/slide1.jpg',
      name: 'To My Soulmate | Prem Warut - 1st Date in Vietnam',
      date:'22/10/2023',
      type:'Theater'
      }, {
      id: 3,
      img: 'https://i.ibb.co/yRx46dT/Slide3.jpg',
      name: 'Hài kịch: Lạc lối ở BangKok',
      date:'22/10/2023',
      type:'Theater'
      },{
      id: 4,
      img: 'https://i.ibb.co/d2hhwZX/Slide4.jpg',
      name: 'TRÁI TIM PHỤ NỮ - TRÁI TIM NGỌC TRAI - CONCERT 01 : HƯƠNG TRĂNG NHƯ NGỌC',
      date:'22/10/2023',
      type:'Live-Music'
      }, {
      id: 5,
      img: 'https://i.ibb.co/c6TjVBs/Slide5.jpg',
      name: 'Yêu Hòa Bình 2023',
      date:'22/10/2023',
      type:'Live-Music'
      },
      {
        id:6,
        img:"https://i.ibb.co/Kj2yF86/sacmau.jpg",
        name:"Kịch IDECAF: Sắc Màu",
        date:'22/10/2023',
      type:'Theater'
      }
    ]
    }
  },
}
</script>
<style>
.main{
margin-bottom: 24px;
position: relative;
}
.home__container{
    margin: 0px auto;
    display: flex;
    min-height: 80%;
    height: 80%;
    flex-direction: column;
}
.main__container{
    /* max-width: 1248px; */
    padding-left: 16px;
    padding-right: 16px;
}
@media (max-width: 1200px) { 
    .main__container{
    max-width: 1248px;
    padding-left: 16px;
    padding-right: 16px;
    }

}
@media (max-width: 992px) { 
    .main__container{
    max-width: 960px;
    padding-left: 16px;
    padding-right: 16px;
    }
    .banner__hidden{
        display: none;
     }
}
@media (max-width: 768px) { 
    .main__container{
    max-width: 720px;
    padding-left: 16px;
    padding-right: 16px;
    }
    .main{
            width: 100%;
            margin-left: 0px;
        }
    .carousel-inner{
        width: 80% !important;
     }
     .banner__hidden{
        display: none;
     }
}
@media (max-width: 576px) { 
    .main__container{
    max-width: 540px;
    padding-left: 16px;
    padding-right: 16px;
    }
    .main{
            width: 100%;
            margin-left: 0px;
        }
    .carousel-inner{
        width: 100% !important;
     }
     .banner__hidden{
        display: none;
     }
}
</style>