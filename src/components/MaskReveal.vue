<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
const tl = gsap.timeline()
tl.from('.mask-title',{
  yPercent:100,duration:1,ease:'power3.out'
})
.from('.mask-img',{
  clipPath:'inset(0% 100% 0% 0%)',
  scale:1.2,
  duration:1.5,
  ease:'power3.out'
},'-=0.5')
})
</script>

<template>
  <section class="mask-section h-screen bg-[#0d0d0d] text-white flex items-center justify-center">

    <div class="text-center">

      <div class="overflow-hidden">
        <h2 class="mask-title text-7xl font-bold">
          Our Vision
        </h2>
      </div>

      <div class="image-wrapper mt-10 overflow-hidden">
        <img
          class="mask-img w-[600px] h-[400px] object-cover"
          src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=1200"
          alt=""
        />
      </div>

    </div>

  </section>
</template>