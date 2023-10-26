<template>
    <div v-show="modalShow">
    <div  class="modal-ready">

    </div>
    <div class="modal-seatmap" style="overflow: hidden auto;" tabindex="-1">
        <div class="modal-seatmap-inner">
            <div class="map-content">
            <div class="map-figure">
                <button v-on:click="modalShow =false" type="button" class="map-close">
                    <b-icon icon="x-lg"></b-icon>
                </button>
                <figure style="cursor: zoom-in;">
                        <img class="mfp-img"
                            src="https://static.ticketmaster.sg/images/activity/field/23_euphony2023_dd028f21b48dced710f997c10541d4c0.jpg"
                            style="max-height: 640px;">
                    </figure>
            </div>
        </div>
        </div>
    </div>
</div>
</template>

<script>
    export default{
        props:['modalShow'],
        methods:{
            closeModal: function () {
            this.modalShow = !this.modalShow;
        },
        }
    }
</script>

<style>
.modal-ready{
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1042;
    overflow: hidden;
    position: fixed;
    background: #0b0b0b;
    opacity: .8;
}
.modal-seatmap{
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1043;
    position: fixed;
    outline: none !important;
    -webkit-backface-visibility: hidden;
}
.modal-seatmap-inner {
    text-align: center;
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    padding: 0 8px;
    box-sizing: border-box;
}
.map-figure{
    cursor: pointer;
}
.map-close{
    color: #FFF;
    right: -6px;
    text-align: right;
    padding-right: 6px;
    width: 100%;
    background-color: transparent;
    border: none !important;
}
.map-content{
    position: relative;
    display: inline-block;
    vertical-align: middle;
    margin: 0 auto;
    text-align: left;
    z-index: 1045;
}
.mfp-img{
    width: auto;
    max-width: 100%;
    height: auto;
    display: block;
    line-height: 0;
    box-sizing: border-box;
    padding: 40px 0 40px;
    margin: 0 auto;
}
</style>