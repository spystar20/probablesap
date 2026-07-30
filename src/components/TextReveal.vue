<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
import SplitType from 'split-type'
gsap.registerPlugin(ScrollTrigger)

onMounted(() => {

  const split = new SplitType('.character-title', {
    types: 'chars'
  })

gsap.from(split.chars,{
 rotateY:90,duration:4,  ease: 'back.out(1.7)'
,opacity:0,stagger:0.03,scale:1,scrollTrigger:{
  trigger:'character-title',start:'top 5%',scrub:true
}
})

})
</script>
<template>
  <div class="bg-black text-white">

    <!-- Just to create scroll distance -->

    <section class="min-h-screen flex items-center justify-center">
  <h2 class="character-title text-6xl font-bold max-w-full">
  Build experiences people remember.
</h2>
    </section>

    <section class="h-screen"></section>

  </div>
</template>
<style scoped>
.description .line {
  overflow: hidden;
}
.line {
  overflow: hidden;
}
.line span {
  display: inline-block;
}
</style>