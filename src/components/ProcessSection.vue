<script setup>
import gsap from 'gsap';
import { onMounted } from 'vue';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
import TextPlugin from 'gsap/TextPlugin';
gsap.registerPlugin(ScrollTrigger,TextPlugin)
onMounted(() => {
  const tl = gsap.timeline({scrollTrigger:{
trigger:'.story',start:'top top',end:'+=300%',pin:true,scrub:true
  }})  
  tl.to('.step-title',{
    y:-50,opacity:0
  })
  .to('.step-title',{textContent:'design',opacity:1,y:0})
  .to('.step-desc',{opacity:0})
      .to(".step-desc", { textContent: "We design clean modern UI.", opacity: 1 })

})
</script>
<template>
  <section class="story h-screen flex items-center justify-center bg-black text-white py-10">

    <div class="text-center space-y-6">

      <h2 class="step-title text-6xl font-bold">Discover</h2>

      <p class="step-desc text-gray-400">
        We start by understanding your idea.
      </p>

      <img
        class="step-img w-[400px] mx-auto rounded-2xl"
        src="https://i.pinimg.com/1200x/21/f5/9c/21f59c5b923c8f866d7da4a87dda0b4d.jpg"
      />

    </div>

  </section>
</template>
<style scoped></style>