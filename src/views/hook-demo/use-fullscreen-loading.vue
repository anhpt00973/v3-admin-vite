<script lang="ts" setup>
import { useFullscreenLoading } from "@/hooks/useFullscreenLoading"
import { getSuccessApi, getErrorApi } from "@/api/hook-demo/use-fullscreen-loading"
import { ElMessage } from "element-plus"

const svg = `
  <path class="path" d="
    M 30 15
    L 28 17
    M 25.61 25.61
    A 15 15, 0, 0, 1, 15 30
    A 15 15, 0, 1, 1, 27.99 7.5
    L 15 15
  " style="stroke-width: 4px; fill: rgba(0, 0, 0, 0)"/>
`

const options = {
  text: "即将发生错误...",
  background: "#F56C6C20",
  svg,
  svgViewBox: "-10, -10, 50, 50"
}

const querySuccess = async () => {
  const res = await useFullscreenLoading(getSuccessApi)()
  ElMessage.success(res.message)
}

const queryError = async () => {
  try {
    await useFullscreenLoading(getErrorApi, options)()
  } catch (err: any) {
    ElMessage.error(err.message)
  }
}
</script>

<template>
  <div class="app-container">
    <h4>Example: bằng cách chuyển chức năng được thực thi cho hook, hãy để hook tự động mở tải toàn màn hình và tự động đóng tải sau khi thực hiện chức năng</h4>
    <el-button @click="querySuccess">Search successful</el-button>
    <el-button @click="queryError">Query failed</el-button>
  </div>
</template>
