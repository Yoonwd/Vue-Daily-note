<template>
  <div class="calendar">
    <full-calendar
      :config="config"
      @day-click="dayClick"
    >

    </full-calendar>
  </div>
</template>

<script>
import { FullCalendar } from "vue-full-calendar";
import 'fullcalendar/dist/fullcalendar.css';

export default {
  name: "Calendar",
  components: {
    FullCalendar
  },
  methods: {
    dayClick(date) {
      let url = `/day/${date.format('YYYY-MM-DD')}`;
      this.$router.push(url);
    }
  },
  computed: {},
  data() {
    return {
      config: {
        defaultView: 'month',
        header: {
          left: 'prev',
          center: 'title',
          right: 'next'
        },
        height: 500
      }
    };
  },
  props: {}
};
</script>
