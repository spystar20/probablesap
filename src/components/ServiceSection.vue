<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { onMounted } from 'vue';
gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    gsap.from('.service-card',{
        y:80,duration:1,opacity:0,stagger:0.2,ease:'power3.out',scrollTrigger:{
            trigger:'.services',start:'top 80%',toggleActions:'play none reset reverse'
        }
    })
})
</script>
<template>
     <section class="services min-h-screen w-full flex flex-col items-center justify-center px-10 py-20">

    <div class="text-center mb-12">
      <h2 class="text-5xl font-bold">What We Do</h2>
      <p class="text-gray-500 mt-3">Simple services. Powerful execution.</p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8 w-full max-w-6xl">

      <div class="service-card p-8 rounded-2xl border border-gray-200 shadow-sm">
        <h3 class="text-2xl font-semibold mb-3">UI Design</h3>
        <p class="text-gray-500">Clean and modern interfaces built for users.</p>
      </div>

      <div class="service-card p-8 rounded-2xl border border-gray-200 shadow-sm">
        <h3 class="text-2xl font-semibold mb-3">Development</h3>
        <p class="text-gray-500">Fast, scalable and responsive web apps.</p>
      </div>

      <div class="service-card p-8 rounded-2xl border border-gray-200 shadow-sm">
        <h3 class="text-2xl font-semibold mb-3">Branding</h3>
        <p class="text-gray-500">Identity systems that stand out.</p>
      </div>

    </div>

  </section>
</template>
<style scoped></style>