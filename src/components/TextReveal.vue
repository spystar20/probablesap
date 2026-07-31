<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
import SplitType from 'split-type'
gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
const blurSplit = new SplitType('.blur-text',{
  types:'words'
})
//   const split = new SplitType('.character-title', {
//     types: 'chars'
//   })
// const newsplit = new SplitType('.color-text', {
//   types: 'words'
// })
// gsap.from(split.chars,{
//  rotateY:90,duration:4,  ease: 'back.out(1.7)'
// ,opacity:0,stagger:0.03,scale:0.5,scrollTrigger:{
//   trigger:'.character-title',start:'top 40%',scrub:true
// }
// })
// gsap.to(newsplit.words,{
//   color:'#fff',duration:0.5,stagger:0.2,scrollTrigger:{
//     trigger:'.color-text',start:'top 45%',end:'top 30%',markers:true,scrub:true
//   }
// })
// gsap.from('.mask-text', {
//   yPercent: 100,
//   duration: 1,
//   ease: 'power4.out',

//   scrollTrigger: {
//     trigger: '.mask',
//     start: 'top 80%',
//     end: 'top 40%',
//     scrub: true,
//     markers: true
//   }
// })
gsap.from(blurSplit.words,{
  filter:'blur(35px)',opacity:0,duration:1,y:50,ease:'bounce.out',scale:0.8,stagger:0.3,scrollTrigger:{
trigger:'.blur-text',start:'top 30%',end:'top 10%',markers:true,scrub:1
  }
})
gsap.from('.clip-text', {
  clipPath: 'inset(100% 100% 100% 100%)',

  scrollTrigger: {
    trigger: '.clip-text',
    start: 'top 30%',
    end: 'top 10%',
    scrub: true,
    markers: true
  }
})
})
</script>
<template>
   


<section class="h-screen flex flex-col gap-3 items-center justify-center bg-black">
<!-- <h2 class="blur-text text-6xl font-bold text-white">
  Build something great.
</h2> -->
<h2 class="clip-text text-6xl font-bold text-white bg-red-400">
  Create something unforgettable.
</h2>
<h2 class="clip-text text-6xl font-bold text-white bg-red-400">
  Create something unforgettable.
</h2>
<h2 class="clip-text text-6xl font-bold text-white bg-red-400">
  Create something unforgettable.
</h2>
</section>

<section class="h-screen bg-black"></section>
</template>

<style scoped>
.mask {
  overflow: hidden;
}

/* .mask-text {
  transform: translateY(100%);
} */
.color-text {
  color: #666;
}
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