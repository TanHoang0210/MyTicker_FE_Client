<template>
 <div style="background-color: #FDF9F7; border-radius: 4px;">
     <banner></banner>
    <main-event :categories="categories"></main-event>
    <footer class="main__footer">
        <router-link class="more--btn" to="/about">
            <div class="main__footer--inner">
                <b-button class="main__footer--btn">
                        Xem Thêm
                </b-button>
            </div>
        </router-link>
    </footer>
 </div>
</template>
<script>
import MainEvent from "@/components/Home/MainComponent/CategoriesComponent.vue/MainEvents.vue"
import Banner from "@/components/Home/MainComponent/CategoriesComponent.vue/Banner.vue"
export default {
    props:['categories'],
    components:{MainEvent,Banner},
    name:"Categories"
}
</script>
<style>
.main__footer{
    width: 100%;
    display: flex;
}
.main__footer--inner{
    width: 100%;
    display: flex;
}
.more--btn{
    width: 30%;
    display: block;
    margin: auto;
    position: relative;
}
.more--btn:hover{
    text-decoration: none;
}
.main__footer--btn{
    width: 100%;
    background-color: var(--text-color)!important;
    color: var(--primary-color) !important;
    font-weight: normal !important;
    font-size: 1.5rem !important;
    border-radius: 2px !important;
}
.main__footer--btn:hover{
    background-color: var(--primary-color)!important;
    color: var(--text-color) !important;
}
.more--btn::before{
    content: "";
    width: 100%;
    background-color: var(--primary-color);
    height: 2px;
    position: absolute;
    bottom: 50%;
    left: -110%;
    border-radius: 88px;
}
.more--btn::after{
    content: "";
    width: 100%;
    background-color: var(--primary-color);
    height: 2px;
    position: absolute;
    bottom: 50%;
    right: -110%;
    border-radius: 88px;
}
</style>