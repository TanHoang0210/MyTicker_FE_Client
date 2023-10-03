<template>
<section>
    <div class="main__container">
        <div class="main__container--inner">
        <div class="event__list"  >
            <div class="event__item" v-for="category in categories">
        <b-card  
              class="mb-3 event__item--info"
              >
              <div class="event__item--img" style="position: relative;">
                  <b-card-img :src="category.img" alt="Image" class="rounded-0"></b-card-img>
                  <router-link to="/about">
                <div class="ticket__button--modal">
                    <button class="ticket__button">
                        <h3 class="ticket__button--title">
                            Get TicKet
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
    width: 100%;
}
.card-body{
    padding: 0 !important;
}
.event__list{
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
}
.event__item{
    width: 32%;
    margin-right: 15px;
    overflow: hidden;
}
.event__item--info{
    border: none;
    height: 90%;
    position: relative;
}
.event__item--img{
    overflow: hidden;
}
.ticket__button--modal{
    top: 0;
    left: -20%;
    position: absolute;
    display: none;
    z-index: 1;
    width: 120%;
    height: 100%;
    background-color: rgb(255,255,255,0.3);
}
.ticket__button{
    background-color: var(--primary-color);
    color: var(--text-color);
    position: absolute;
    right: -30px;
    width: 10%;
    height: 100%;
    opacity: 0.1;
    transition: all ease-in 0.3s;
    writing-mode: vertical-rl;
    text-orientation: upright;
    display: flex;
    align-items: center;
    border: none;
    border-radius: none !important;
    opacity: 0.5;
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
    color: var(--text-color);
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
    font-size: 1.2em;
  writing-mode: vertical-lr;
  text-orientation: sideways-right;
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