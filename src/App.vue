<script setup>
import DxButton from 'devextreme-vue/button';
function showMessage() {
  alert("HEllo Developers")
}
import SelectItem from './components/SelectItem.vue';
import Form from './components/Form/Form.vue';
import DataBinding from './components/Data Binding/DataBinding.vue';
</script>

<template>
  <header class="max-w-300 m-auto">
    <div>Dev extrem</div>
    <DxButton text="Click me!" @click="showMessage()" />
    <SelectItem />
    <Form/>
<DataBinding/>
  </header>
  <main>

  </main>
</template>

<style scoped></style>
