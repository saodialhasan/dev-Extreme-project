<template>
    <div id="list-demo">
      <div class="widget-container">
        <DxList
          v-model:selected-item-keys="selectedItemKeys"
          :data-source="dataSource"
          :height="400"
          :show-selection-controls="true"
          :selection-mode="selectionMode"
          :select-all-mode="selectAllMode"
          :select-by-click="selectByClick"
        />
        <div class="selected-data">
          <span class="caption">Selected IDs: </span>
          <span>{{ selectedItemKeys.join(", ") }}</span>
        </div>
      </div>
      <div class="options">
        <div class="caption">Options</div>
        <div class="option">
          <span>Selection Mode </span>
          {{ " " }}
          <DxSelectBox
            v-model:value="selectionMode"
            :items="['none', 'single', 'multiple', 'all']"
            :input-attr="{ 'aria-label': 'Selection Mode' }"
          />
        </div>
        <div class="option">
          <span>Select All Mode </span>
          {{ " " }}
          <DxSelectBox
            v-model:value="selectAllMode"
            :disabled="selectionMode !== 'all'"
            :input-attr="{ 'aria-label': 'Select All Mode' }"
            :items="['page', 'allPages']"
          />
        </div>
        <div class="option">
          <span>Select By Click </span>
          {{ " " }}
          <DxCheckBox
            v-model:value="selectByClick"
            :element-attr="{ 'aria-label': 'Selection By Click' }"
          />
        </div>
      </div>
    </div>
  </template>
  <script setup lang="ts">
  import { ref } from 'vue';
  import type { SingleMultipleAllOrNone } from 'devextreme-vue/common';
  import DxSelectBox from 'devextreme-vue/select-box';
  import DxList, { type DxListTypes } from 'devextreme-vue/list';
  import DxCheckBox from 'devextreme-vue/check-box';
  import ArrayStore from 'devextreme/data/array_store';
import { tasks } from './data';
  
  const dataSource = new ArrayStore({
    key: 'id',
    data: tasks,
  });
  const selectedItemKeys = ref([]);
  const selectionMode = ref<SingleMultipleAllOrNone>('all');
  const selectAllMode = ref<DxListTypes.SelectAllMode>('page');
  const selectByClick = ref(false);
  </script>
  <style>
  .selected-data,
  .options {
    margin-top: 20px;
    padding: 20px;
    background-color: rgba(191, 191, 191, 0.15);
  }
  
  .selected-data .caption {
    font-weight: bold;
    font-size: 115%;
  }
  
  .options .caption {
    font-size: 18px;
    font-weight: 500;
  }
  
  .option {
    margin-top: 10px;
  }
  
  .option > span {
    width: 120px;
    display: inline-block;
  }
  
  .option > .dx-widget {
    display: inline-block;
    vertical-align: middle;
    width: 100%;
    max-width: 350px;
  }
  </style>