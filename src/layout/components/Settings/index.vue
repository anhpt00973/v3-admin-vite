<script lang="ts" setup>
import { useSettingsStore } from "@/store/modules/settings"

const settingsStore = useSettingsStore()
</script>

<template>
  <div class="drawer-container">
    <div>
      <h3 class="drawer-title">Cấu hình bố trí hệ thống</h3>
      <div class="drawer-item">
        <span>Hiển thị thanh tab</span>
        <el-switch v-model="settingsStore.showTagsView" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Logo thanh bên</span>
        <el-switch v-model="settingsStore.showSidebarLogo" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Header cố định</span>
        <el-switch v-model="settingsStore.fixedHeader" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Thông báo tin nhắn</span>
        <el-switch v-model="settingsStore.showNotify" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Nút chủ đề chuyển đổi</span>
        <el-switch v-model="settingsStore.showThemeSwitch" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Nút toàn màn hình</span>
        <el-switch v-model="settingsStore.showScreenfull" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Chế độ màu xám</span>
        <el-switch v-model="settingsStore.showGreyMode" class="drawer-switch" />
      </div>
      <div class="drawer-item">
        <span>Chế độ đảo màu</span>
        <el-switch v-model="settingsStore.showColorWeakness" class="drawer-switch" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.drawer-container {
  padding: 24px;
  font-size: 14px;
  line-height: 1.5;
  word-wrap: break-word;
  .drawer-title {
    margin-bottom: 12px;
    font-size: 14px;
    line-height: 22px;
  }
  .drawer-item {
    font-size: 14px;
    padding: 12px 0;
  }
  .drawer-switch {
    float: right;
  }
}
</style>
