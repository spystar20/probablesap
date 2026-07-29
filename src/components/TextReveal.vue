<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
import SplitType from 'split-type'


onMounted(()=>{
  const split = new SplitType('.description',{
 types:'lines'
  })
    gsap.from('.line h2',{
        yPercent:100,ease:'power4.out',duration:1
    }),
    gsap.from('.line span',{
      yPercent:100,ease:'power4.out',  duration:1,  stagger:0.2
    })
    gsap.from(split.lines,{
  yPercent: 100,
    duration: 1,
    stagger: 0.15,
    ease: 'power4.out',scrollTrigger:{
      start:'top ',end:'top +=300',scrub:true
    }

    })
})
</script>
<template>
  <div class="flex flex-col p-10 bg-black text-white">
    <div class="line  text-white text-4xl text-center">
  <h2>Build beautiful experiences</h2>
</div>
<div class="flex flex-col text-center text-4xl font-semibold text-white">
  <div class="line ">
  <span>Build</span>
  </div>
  <div class="line ">
  <span>Beautiful
</span>
  </div>
  <div class="line ">
  <span>experiences
</span>
  </div>
</div>
<p class="description text-4xl font-semibold max-w-md">
  We create beautiful digital experiences for modern brands.
</p>
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