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
// gsap.fromTo('.parallax-container',
//     {
// backgroundPosition:'center 60%'    },{
//         backgroundPosition:'center 80%',scrollTrigger:{
//             trigger:'.parallax-container',start:'top bottom',end:'bottom top',scrub:true
//         }
//     }
// )
// const tl = gsap.timeline({
//   scrollTrigger:{
//     trigger:'.horizontal-scene',
//     start:'top 20%',
//     end:'bottom top',
//     scrub:true,
//     markers:true
//   }
// })
// tl.to('.img-1',{xPercent:-10},0)
// .to('.img-2',{
//   xPercent:-25
// },0)
// .to('.img-3',{
//   xPercent:20
// },0)
// .to('.img-4',{
//   xPercent:35
// },0)
// tl.to('.layer-bg',{
//   yPercent:5
// },0)
// .to('.layer-middle',{
//   yPercent:15},0)

//   .to('.layer-front',{
//     yPercent:25
//   },0)
gsap.fromTo('.parallax-img',
  {
    yPercent: -10,
    scale: 1.1
  },
  {
    yPercent: 10,
    scale: 1,

    scrollTrigger: {
      trigger: '.parallax-container',
      start: 'top 80%',
      end: 'bottom 20%',
      scrub: true,
      markers: true
    }
  }
)
})
</script>
<template>
  <section class="min-h-screen bg-black"></section>
<section class="parallax-container h-screen w-full overflow-hidden bg-black">

  <div
    class="parallax-img h-[120%] w-full bg-cover bg-center"
    style="background-image: url('https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=1600')"
  ></div>

</section>

<section class="h-screen bg-black"></section>



<section class="h-screen bg-black"></section>
</template>
<style scoped></style>