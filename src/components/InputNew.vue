<template>
    <form action="" @submit.prevent="handleSubmit">
        <input type="text" name="" id="input-name-item" v-model="text">
    </form>
</template>
<script lang="ts" setup>
import { ref, defineEmits } from 'vue';

const text = ref("")
// Emitir un valor desde un componente hijo a su componente padre permite 
// establecer una comunicación entre ellos. 
// El componente hijo emite un evento con un valor asociado, y el 
// componente padre puede escuchar ese evento y acceder al valor emitido.
const emits = defineEmits(["onNewItem"])

function handleSubmit() {
    if (text.value != "") {
        emits("onNewItem", text.value);
        text.value = "";
    }
}
</script>
<style scoped></style>