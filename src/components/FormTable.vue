<template>
    <div id="app-container">
        <DxForm id="form">
            <!-- Configuration goes here -->
        </DxForm>
    </div>
</template>
 
<script>
import 'devextreme/dist/css/dx.light.css';
 
import { DxForm } from 'devextreme-vue/form';
 
export default {
    components: {
        DxForm
    }
}
</script>
 
<style>
#form {
    height: 400px;
}
</style>