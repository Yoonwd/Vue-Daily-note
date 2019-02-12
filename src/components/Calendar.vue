<template>
  <div class="calendar">
    <div class="calendar-inner">
      <h1>Calendar</h1>
      <router-link class="button" :to="todayUrl"> START </router-link>
    </div>
  </div>
</template>

<script>
import moment from "moment";

export default {
  name: "Calendar",
  methods: {},
  computed: {},
  data() {
    return {};
  },
  props: {}
};
</script>
