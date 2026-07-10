<script setup>
import { onMounted } from "vue"
import gsap from "gsap"
import ScrollTrigger from "gsap/ScrollTrigger"

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  ScrollTrigger.create({
    trigger: ".box",
    start: "top top",
    end: "+=500",
    pin: true,
    markers: true
  })
})
</script>

<template>
  <section class="box h-screen bg-red-500 flex items-center justify-center">
    <h1 class="text-6xl text-white">PIN ME</h1>
  </section>

  <section class="h-screen bg-blue-500 flex items-center justify-center">
    <h1 class="text-6xl text-white">SECOND</h1>
  </section>
</template>