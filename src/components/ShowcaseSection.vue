<script setup>
import gsap from 'gsap';
import { onMounted } from 'vue';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger)
onMounted(() => {
   const wrapper = document.querySelector('.showcase-wrapper')
const scrollDistance = wrapper.scrollWidth - window.innerWidth
gsap.from(wrapper,{
    x:-scrollDistance,
    scrollTrigger:{
        trigger:'.showcase-section',
        start:'top top',end:`+=${scrollDistance}`,pin:true,scrub:true
    }
})
gsap.from('.card',{
    scale:0.8,opacity:0,stagger:0.2,ease:'power2',scrollTrigger:{
        trigger:'.showcase-section' ,start:'top top',
    }
})
})
</script>
<template>
      <section class="showcase-section h-screen overflow-hidden bg-black text-white">

    <div class="showcase-wrapper flex gap-10 w-max h-full items-center px-20">

      <div v-for="n in 6" :key="n"
        class="card w-[500px] h-[350px] rounded-2xl bg-white text-black flex items-center justify-center text-3xl font-bold">
        Project {{ n }}
      </div>

    </div>

  </section>
</template>
<style scoped></style>