<script lang="ts" setup>
import { useFetchSelect } from "@/hooks/useFetchSelect"
import { getSelectDataApi } from "@/api/hook-demo/use-fetch-select"

const { loading, options, value } = useFetchSelect({
  api: getSelectDataApi
})
</script>

<template>
  <div class="app-container">
    <h4>Example: lấy dữ liệu mà thành phần Select cần sau khi gọi api tự động thông qua hook và chuyển nó đến thành phần Select</h4>
    <h5>Select example</h5>
    <el-select :loading="loading" v-model="value" filterable>
      <el-option v-for="(item, index) in options" v-bind="item" :key="index" placeholder="please choose" />
    </el-select>
    <h5>Select V2 example(nếu lượng dữ liệu nhiều có thể chọn thành phần này)</h5>
    <el-select-v2 :loading="loading" v-model="value" :options="options" filterable placeholder="please choose" />
  </div>
</template>
