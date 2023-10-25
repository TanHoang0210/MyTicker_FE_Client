<template>
    <div class="aboutEvent">
        <ticket-list :currentEvent="currentEvent" :listTickets="listTickets"></ticket-list>
        <event-detail :currentEvent="currentEvent"></event-detail>
        <ticket-price :currentEvent="currentEvent"></ticket-price>
        <section id="eventFAQ">
            faq
        </section>
        <section id="eventPolicy">
            policy
        </section>
    </div>
</template>
<script>
import TicketList from '@/components/Home/EventDetailComponent/AboutEventComponent/TicketList.vue'
import EventDetail from '@/components/Home/EventDetailComponent/AboutEventComponent/EventDetail.vue'
import TicketPrice from '@/components/Home/EventDetailComponent/AboutEventComponent/TicketPrice.vue'
export default {
  name: 'EventDetailView',
  props:['currentEvent','listTickets'],
  components:{
    TicketList,EventDetail,TicketPrice
  }
}
</script>
<style></style>