<script setup>
import { ref, reactive, onMounted, watch } from "vue"
import { useRouter } from 'vue-router'
import ProductDetail from '@/components/ProductDetail.vue'
const product ="dsdsd"
const count = ref(0)
const inputText = ref('wwwww')
const doituong = reactive({
    tite: "vueJS",
    name: "Tuanvo"
})

const chuyenTrang = ()=> {
router.push({name: 'about'})
}
const router = useRouter()
doituong.tite = "dat thay doi title"


onMounted(() => {
    setTimeout(() => {
        toDu.value = "moutech thay doi r"    
    }, 3000)
})

const toDu = ref('mound chua thay doi')

watch(toDu, ()=>{
    chuyenTrang()
})

watch(count, ()=>{
    inputText.value ='count cong len ' + count.value
})

</script>
<template>
<div>
    <h1>{{ product }}</h1>
    <div>{{ count }}</div>
    <div>{{ doituong.tite }}</div>
    <button @click="count++">New++</button>
    <button @click="chuyenTrang">chuyen trang</button>
    <div>title input: {{ inputText }}</div>
    <!-- <button @click="router.push({name:'home'})"> day</button> -->
    <input type="text" v-model="inputText">
    <router-link to="/setting"><button>product</button></router-link>
    <ProductDetail
    :doituong=doituong
    :inputText=inputText
    :count=count
    />
    <div>{{ toDu }}</div>
</div>
</template>

<style scoped>
div{
    padding: 15px 5px;
}
</style>
