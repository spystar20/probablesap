<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
import SplitType from 'split-type'
gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
//  gsap.fromTo(
//   '.mask-img',
//   {
//     clipPath: 'circle(0% at 50% 50%)'
//   },
//   {
//     clipPath: 'circle(120% at 50% 50%)',
//     duration: 6,
//     ease: 'power4.out'
//   }
// )
gsap.fromTo('.parallax-container',
    {
backgroundPosition:'center 60%'    },{
        backgroundPosition:'center 80%',scrollTrigger:{
            trigger:'.parallax-container',start:'top bottom',end:'bottom top',scrub:true
        }
    }
)
})
</script>
<template>
   <section class="h-screen bg-red-500"></section>

<section class="h-screen bg-black flex items-center justify-center">

  <div
    class="parallax-container w-full h-screen bg-cover bg-center overflow-hidden"
    style="background-image: url('https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=1200')"
  >
  </div>

</section>

<section class="h-screen bg-blue-500"></section>
</template>
<style scoped></style>