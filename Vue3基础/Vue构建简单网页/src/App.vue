<script setup>
import {ref} from 'vue'

// 创建一个变量来记录选项卡的状态
const current = ref(0)    //0表示球员，1表示球队


</script>
<template>
  <!-- 选项卡的外部容器 -->
  <div class="tab-wrapper">
    <!-- 选项卡的头部 -->
    <header class="tab-head">
      <!-- 定义两个按钮 -->
      <div @click="current  = 0" class="tab-button" :class="{active:current === 0}">热门球员</div>
      <div @click="current = 1" class="tab-button" :class="{active:current === 1}">热门球队</div>
    </header>
    <!-- 选项卡主体内容 -->
    <div class="main">
      <!-- 
        v-show 指令，接受一个布尔值作为判断，用来设置一个内容是否显示
          v-show是通过display来设置一个元素是否显示的
       -->
       <div v-show="current === 0">
        <!-- 球员 -->
        <div class="tab-lits">
          <div class="tab-item">
            <!-- 图片 -->
            <div class="photo">
              <img src="../public/images/messi.png" alt="梅西">
              <span>1</span>
            </div>
            <!-- 描述 -->
            <div class="desc">
              <span class="name">梅西</span>
              <div class="hot-bar">
                <div class="inner">433760热度</div>
              </div>
            </div>
          </div>
        </div>
      
      </div>
       <div v-show="current === 1">
        <!-- 球队 -->
        <div class="tab-lits">
          <div class="tab-item">
            <!-- 图片 -->
            <div class="photo">
              <img src="../public/images/法国.jpg" alt="法国">
              <span>1</span>
            </div>
            <!-- 描述 -->
            <div class="desc">
              <span class="name">法国</span>
              <div class="hot-bar">
                <div class="inner">433760热度</div>
              </div>
            </div>
          </div>
        </div>
        
      </div>
    </div>
  </div>
</template>

<style scoped>
  .tab-wrapper {
    box-sizing: border-box;
    width: 800px;
    padding: 20px;
    background-color: rgb(45, 83, 211);
  }

  .tab-head {
    display: flex;
    border-radius: 10px;
    overflow: hidden;
  }

  .tab-button {
    background-color: white;
    font-size: 30px;
    padding: 10px 0;
    text-align: center;
    flex: auto;
    cursor: pointer;
    transition: 0.5s;
  }
.tab-button:not(.active):hover {
  color:rgb(187, 3, 52)
}
  .active {
    background-color: rgb(187,3,52);
    color:white
  }
</style>