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
// gsap.fromTo('.parallax-img',
//   {
//     yPercent: -10,
//     scale: 1.1
//   },
//   {
//     yPercent: 10,
//     scale: 1,

//     scrollTrigger: {
//       trigger: '.parallax-container',
//       start: 'top 80%',
//       end: 'bottom 20%',
//       scrub: true,
//       markers: true
//     }
//   }
// )
const images = gsap.utils.toArray('.interior-img')
const items = gsap.utils.toArray('.project-item')
items.forEach(item=>{
  item.addEventListener('mouseenter',()=>{
    gsap.to(images,{
      opacity:1,scale:1,stagger:0.1,duration:0.5,ease:'back.out(1.7)'
    })
  })
})
})
</script>
<template>
  <section class="min-h-screen bg-black"></section>
<!-- <section class="parallax-container h-screen w-full overflow-hidden bg-black">

  <div
    class="parallax-img h-[120%] w-full bg-cover bg-center"
    style="background-image: url('https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=1600')"
  ></div>

</section> -->


<section class="gallery-section min-h-screen bg-black text-white flex items-center justify-center">

  <div class="project-list">

    <div class="project-item" data-project="interior">
      Interior Design
    </div>

    <div class="project-item" data-project="architecture">
      Architecture
    </div>

    <div class="project-item" data-project="branding">
      Branding
    </div>

    <div class="project-item" data-project="fashion">
      Fashion
    </div>

  </div>

  <!-- Images -->
  <div class="image-container">

    <img
      class="project-image interior-img img-1"
      src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=800"
    />

    <img
      class="project-image interior-img img-2"
      src="https://images.unsplash.com/photo-1497366811353-6870744d04b2?w=800"
    />

    <img
      class="project-image interior-img img-3"
      src="https://images.unsplash.com/photo-1497366216548-37526070297c?w=800"
    />

  </div>

</section>

<section class="h-screen bg-black"></section>
</template>
<style scoped>
.gallery-section {
  position: relative;
}

.project-list {
  position: relative;
  z-index: 10;
}

.project-item {
  font-size: 4rem;
  cursor: pointer;
}

.image-container {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.project-image {
  position: absolute;
  width: 250px;
  height: 320px;
  object-fit: cover;
  opacity: 0;
  scale: 0.5;
}
.img-1 {
  top: 20%;
  left: 25%;
}

.img-2 {
  top: 40%;
  left: 45%;
}

.img-3 {
  top: 15%;
  left: 60%;
}
</style>