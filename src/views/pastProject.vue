<template>
    <div class="demo-collapse">
      <el-collapse accordion>
        <el-collapse-item name="1">
          <template #title="{ isActive }">
            <div :class="['title-wrapper', { 'is-active': isActive }]">
              {{ $t ('past.projectName1') }}
              <el-icon class="header-icon">
                <info-filled />
              </el-icon>
            </div>
          </template>
          <div>
            {{ $t ('past.projectDescrip1')}}
          </div>
          <div>
            {{ $t ('past.projectLink1')}}
          </div>
        </el-collapse-item>
        <el-collapse-item name="2">
          <template #title="{ isActive }">
            <div :class="['title-wrapper', { 'is-active': isActive }]">
              {{ $t ('past.projectName2') }}
              <el-icon class="header-icon">
                <info-filled />
              </el-icon>
            </div>
          </template>
          <div>
            {{ $t ('past.projectDescrip2')}}
          </div>
          <div>
            {{ $t ('past.projectLink2')}}
          </div>
        </el-collapse-item>
        <el-collapse-item name="3">
            <template #title="{ isActive }">
            <div :class="['title-wrapper', { 'is-active': isActive }]">
                {{ $t ('past.projectName3') }}
                <el-icon class="header-icon">
                <info-filled />
                </el-icon>
            </div>
            </template>
          <div>
            {{ $t ('past.projectDescrip3')}}
          </div>
          <div>
            {{ $t ('past.projectLink3')}}
          </div>
        </el-collapse-item>
      </el-collapse>
    </div>
  </template>
  
  <script setup lang="ts">
  import { InfoFilled } from '@element-plus/icons-vue'
  </script>
  
  <style scoped>
  .title-wrapper {
    display: flex;
    align-items: center;
    gap: 4px;
  }
  
  .title-wrapper.is-active {
    color: var(--el-color-primary);
  }

  .el-collapse-item{
    margin-left: 20px;
    margin-right: 20px;
  }
  
  </style>
  