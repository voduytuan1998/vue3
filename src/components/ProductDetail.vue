<script setup>
import { defineProps } from "vue";

const props =  defineProps(['inputText'])
</script>
<template>
    <div>
    <h1>componte con</h1>
    <h2>{{ props.inputText  }}</h2>
    </div>
</template>