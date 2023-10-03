<template>
<section style="display: flex; margin-bottom: 20px;">
    <div class="main__container">
        <div class="main__container--inner">
        <div class="event__list"  >
            <div class="event__item--inner" v-for="category in categories">
            <div class="event__item">
                    <b-card  
              class="mb-3 event__item--info"
              >
              <div class="event__item--img" style="position: relative;">
                  <b-card-img :src="category.img" alt="Image" class="rounded-0"></b-card-img>
                  <router-link to="/about">
                <div class="ticket__button--modal">
                    <button class="ticket__button">
                        <h3 class="ticket__button--title">
                            >
                        </h3>
                    </button>
                </div>
            </router-link>
              </div>
              <b-card-tittle>{{category.name}}</b-card-tittle>
              <b-card-sub-title>{{ category.date }}</b-card-sub-title>
              <b-card-text class="event__item--type">
                {{category.type}}
              </b-card-text>
      </b-card>
            </div>
            </div>
        </div>
    </div>
    </div>
</section>
</template>
<script>
export default{
    props:['categories'],
}
</script>
<style scoped>
.main__container{
    display: flex;
}
.main__container--inner{
    margin: auto;
    width: 80%;
    display: flex;
}
.card-body{
    padding: 0 !important;
    border-radius: 5px 5px !important;
}
.event__list{
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
}
.event__item--inner{
    width: 33.33%;
}
.event__item{
    width: 100%;
    height: 100%;
    overflow: hidden;
    display: flex !important;
    margin: auto !important;
}
.event__item--info{
    height: 95%;
    margin: auto;
    border: none;
    width: 95%;
    position: relative;
}
.event__item--img{
    overflow: hidden;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
}
.ticket__button--modal{
    top: 0;
    left: -20%;
    position: absolute;
    display: none;
    z-index: 1;
    width: 120%;
    height: 100%;
}
.ticket__button{
    background-color: var(--primary-color-bold);
    color: var(--primary-color);
    position: absolute;
    right: -30px;
    width: 5%;
    height: 100%;
    opacity: 0.1;
    transition: all ease-in 0.3s;
    writing-mode: vertical-rl;
    text-orientation: upright;
    display: flex;
    align-items: center;
    border: none;
    border-radius: none !important;
    opacity: 0.8;
}
.event__item--img:hover .ticket__button--modal{
    display: block;
    cursor: pointer;
}
.ticket__button--modal:hover .ticket__button{
    right: 0;
}
.card-img{
    transition: all ease-out 0.3s !important;
}
.event__item--img:hover .card-img{
    transform: perspective(800px) translateZ(50px) !important;
}
.ticket__button--modal:hover .ticket__button{
    opacity: 0.8;
    color: var(--primary-color);
}
.ticket__button:hover{
    opacity: 1;
}
.ticket__button:focus{
    border: none !important;
    background-color: var(--primary-color) !important;
    text-align: center;
}
.ticket__button--title {
    font-size: 1.6em;
}
@media only screen and (max-width: 1290px) {
    .event__item{
        width: 47%;
}
}
@media only screen and (max-width: 960px) {
    .event__item{
        width: 100%;
}
}
@media only screen and (max-width: 769px) {
    .event__item{
    width: 100%;
}
}
@media only screen and (max-width: 577px) {
    .event__item{
    width: 100%;
}
}

</style>