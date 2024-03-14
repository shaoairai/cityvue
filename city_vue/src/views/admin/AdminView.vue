<script>
import { RouterView } from "vue-router";
import LogoIcon from "@/components/icons/LogoIcon.vue";

export default {
  data() {
    return {
      selectedOption: "aicam",
    };
  },
  components: {
    LogoIcon,
    RouterView,
  },
  methods: {
    handleChange() {
      // option 切換 Router
      this.$router.push({ path: "/admin/" + this.selectedOption });
    },
  },
};
</script>

<template>
  <div>
    <div
      class="d-flex justify-content-between align-items-center border-bottom px-3"
      style="height: 70px"
    >
      <div class="d-flex">
        <div class="d-flex align-items-center">
          <LogoIcon style="font-size: 42px"></LogoIcon>
          <h2 class="fs-5 m-0 ms-2 fw-bold">AI 精準消防平台</h2>
        </div>
        <span class="h-100 bg-white" style="width: 1px"></span>
        <select v-model="selectedOption" @change="handleChange">
          <option value="aicam">AI 監視器影像辨識系統</option>
          <option value="radio">任務無線電辨識系統</option>
        </select>
      </div>
      <div>帳號設定</div>
    </div>
  </div>

  <RouterView></RouterView>
</template>
