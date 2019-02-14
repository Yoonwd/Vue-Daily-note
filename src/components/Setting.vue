<template>
  <div class="setting">
    <div class="setting-inner">
      <h1>Setting</h1>
      <form @submit.prevent="saveSettings">
        <fieldset>
          <label for="starttime">시작 시간</label>
          <select id="starttime" 
            v-model="settings.starttime">
            <option value="06:00">06:00</option>
            <option value="07:00">07:00</option>
            <option value="08:00">08:00</option>
          </select>
        </fieldset>
        <fieldset>
          <label for="lang">달력 언어</label>
          <select id="lang" v-model="settings.lang">
            <option value="ko">한국어</option>
            <option value="en">English</option>
          </select>
        </fieldset>
        <fieldset class="submit">
          <button type="submit" class="save">
            저장
          </button>
        </fieldset>
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import { mapGetters, mapActions } from 'vuex';

export default {
  name: "Setting",
  methods: {
    ...mapActions(['saveSettings']),
    saveSettings() {
      let url = 
      `https://vue-daily-report-2ab66.firebaseio.com/settings.json`;
      axios.put(url, this.settings).then((res) => {
        this.saveSettings(this.settings);
        alert('저장이 완료되었습니다');
      });
    },
    getSettings() {
      this.settings = this.savedSettings;
    }
  },
  computed: {
    ...mapGetters(['savedSettings'])
  },
  data() {
    return {
      settings: {
        starttime: '06:00',
        lang: 'ko'
      }
    };
  },
  created() {
    this.getSettings();
  }
};
</script>
