<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
onMounted(()=>{
    gsap.from('.line h2',{
        yPercent:100,ease:'power4.out',duration:1
    })
})
</script>
<template>
    <div class="line bg-black text-white text-4xl text-center p-10">
  <h2>Build beautiful experiences</h2>
</div>
</template>
<style scoped>
.line {
  overflow: hidden;
}</style>