<!--/**
 * @author: liuk
 * @date: 2023/1/9
 * @describe: vue实现虚拟表单
 * @solution:
    1.确定可视区域的高度
    2.确定内容区域的总高度，用背景div撑起假的滚动条
    3.通过scroll事件确定显示内容，并用 transform实现实际内容区域移动到指定位置
*/-->
<template>
  <div>
    <h2>vue实现虚拟表单</h2>
    <div class="list-view" :style="{height:`${viewHeight}px`}" @scroll="handleScroll">
      <div
          class="list-view-bg"
          :style="{height:bgHeight}"
      ></div>
      <ul ref="conRef" class="list-view-content">
        <li
            class="list-view-item"
            v-for="(item,index) in vData"
            :key="index"
            :style="{height:`${itemHeight}px`}"
        >
          {{ item?.label }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts" setup>

import {reactive, ref, toRefs, computed} from 'vue'
import _ from "lodash";
// refs
const conRef = ref<any>();

const bgHeight = computed(() => `${model.data.length * model.itemHeight}px`)
const model = reactive({
  data: <any>[],
  vData: <any>[],
  viewHeight: 400,
  itemHeight: 30
})
const {data, vData, viewHeight, itemHeight} = toRefs(model)

const handleScroll = (val: any) => {
  let scrollTop: number = val.target.scrollTop
  updateVdata(scrollTop)
}

const updateVdata = (scrollTop: number) => {
  // 获取可见区域的可见列表数量
  const vNum = Math.ceil(model.viewHeight / model.itemHeight)
  // 获取可见区域的开始数据索引
  const start = Math.floor(scrollTop / model.itemHeight)
  // 获取可见区域的结束数据索引
  const end = start + vNum;
  // 计算出可见区域的数据，让vue更新
  model.vData = model.data.slice(start, end)
  // 下拉到可视区域
  conRef.value.style.transform = `translate(0, ${start * model.itemHeight}px`
}

// 异步数据
setTimeout(() => {
  model.data = _.fill(new Array(100), {label: 2})
  updateVdata(0)
})

</script>

<style lang="scss" scoped>
.list-view {
  overflow: auto;
  position: relative;
  width: 200px;
  border: 1px solid #aaa;
  height: 300px;

  .list-view-bg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    z-index: -1;
  }

  .list-view-content {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    list-style: none;
    padding: 0;
    margin: 0;

    .list-view-item {
      padding: 5px;
      color: #666;
      line-height: 30px;
      box-sizing: border-box;
    }
  }
}
</style>


