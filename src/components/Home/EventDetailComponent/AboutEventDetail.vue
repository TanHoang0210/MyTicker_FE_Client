<template>
    <div class="aboutEvent">
        <ticket-list :currentEvent="currentEvent" :listTickets="listTickets"></ticket-list>
        <event-detail :currentEvent="currentEvent"></event-detail>
        <section id="ticketPrice">
            price
        </section>
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
export default {
  name: 'EventDetailView',
  props:['currentEvent','listTickets'],
  components:{
    TicketList,EventDetail
  }
}
</script>
<style></style>