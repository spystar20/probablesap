<script setup>
import gsap from 'gsap';
import { onMounted } from 'vue';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
const tl = gsap.timeline()
tl.from('.hero-title',{
    yPercent:100,opacity:0,duration:1.2, ease:'power3.out'
})
.from('.hero-subtitle',{
        yPercent:40,opacity:0,duration:1, ease:'power3.out'

},'-=0.6')
.from('.hero-btn',{
            yPercent:30,opacity:0,duration:1, ease:'power3.out'

},'-=0.5')
gsap.to('.hero',{
opacity:0,scale:0.95,scrollTrigger:{
    trigger:'.hero',start:'top top' ,end:"bottom top",scrub:true
}
})
})
</script>
<template>
<div class="hero w-full bg-black text-white relative overflow-hidden h-screen flex flex-col justify-center items-center">
    <div class="text-center space-y-6">
<div class="overflow-hidden">
    <h2 class="hero-title font-bold text-6xl">
                  Build Stunning Experiences

    </h2>
    
</div>
<div class="overflow-hidden">
    <h2 class="hero-subtitle text-lg text-gray-300">
          Learn GSAP by building real animations step by step

    </h2>
    
</div>
<div class="overflow-hidden">
    <h2 class="hero-btn text-lg px-6 py-3  bg-white text-black rounded-xl">
          Get Started

    </h2>
    
</div>
    </div>
</div>
<div class="bg-red-600 h-screen"> </div>
</template>
<style scoped></style>