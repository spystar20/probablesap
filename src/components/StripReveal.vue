<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
onMounted(() => {
gsap.from('.strip',{
    rotateY:(index) => index % 2 === 0 ? 90 : -90,stagger:0.15,duration:1,ease:'power3.out', scrollTrigger: {
      trigger: '.strip-container',
      start: 'top 80%',
      end: 'top 20%',
      scrub: true,
      markers: true
    }
})
})
</script>

<template>

  <section class="h-screen strip-container bg-[#0d0d0d] flex items-center justify-center">

    <div class="strip-container w-[700px] h-[500px] flex overflow-hidden">
<div class="strip strip-1"></div>
<div class="strip strip-2"></div>
<div class="strip strip-3"></div>
<div class="strip strip-4"></div>
<div class="strip strip-5"></div>

    </div>

  </section>

</template>

<style scoped>
.strip-container{
    perspective: 1000px;
}
.strip {
  width: 20%;
  height: 100%;
  background-image: url("https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=1200");
  background-size: 500% 100%;
}

.strip-1{
    background-position: 0% 0%;
}
.strip-2{
    background-position: 25% 0%;
}
.strip-3{
    background-position: 50% 0%;
}
.strip-4{
    background-position: 75% 0%;
}
.strip-5{
    background-position: 100% 0%;
}
</style>