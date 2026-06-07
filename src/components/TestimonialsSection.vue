<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
  const img = document.querySelector('.step-img')
  const tl = gsap.timeline({scrollTrigger:{
  pin:true,start:'top top',end:'+=300%',trigger:'.story',

}})

gsap.set('.img-2,.img-3,.img-4',{
  y:100,opacity:0
})
tl.to('.img-div',{

  scrollTrigger:{
  start:'top top',end:'+=300%',markers:true,trigger:'.img-div'
  }
})
tl.to('.img-2',{
  y:0,opacity:1,duration:1,scrollTrigger:{
    scrub:true,start:'top top',end:'bottom top',trigger:'.img-2'
  }
})
.to('.img-3',{
  y:0,opacity:1,duration:1,scrollTrigger:{
    scrub:true,start:'top top',end:'bottom top',trigger:'.img-3'
  }
})
.to('.img-4',{
  y:0,opacity:1,duration:1,scrollTrigger:{
    scrub:true,start:'top top',end:'bottom top',trigger:'.img-4'
  }
})
})
</script>
<template>
  <section
    class="story relative h-screen overflow-hidden bg-[#0f0f0f] text-white flex items-center px-20"
  >
    <!-- Left Content -->
    <div class="w-1/2 z-10">
      <p
        class="uppercase tracking-[0.3em] text-sm text-gray-400 mb-4"
      >
        Creative Process
      </p>

      <div class="overflow-hidden">
        <h2 class="step-title text-7xl font-bold leading-none">
          Discover
        </h2>
      </div>

      <div class="overflow-hidden mt-6">
        <p class="step-desc text-lg text-gray-400 max-w-lg leading-relaxed">
          We begin by understanding your goals, audience, and vision to
          create experiences that truly connect with people.
        </p>
      </div>

      <div class="mt-10">
        <span
          class="border border-white/20 px-4 py-2 rounded-full text-sm"
        >
          Step 01 / 04
        </span>
      </div>
    </div>

    <!-- Right Image -->
    <div class="w-1/2 flex justify-center items-center">
    <div class="img-div relative w-[650px] h-[450px]">

  <img src="https://i.pinimg.com/736x/c4/2d/75/c42d75034b46507b6cb3390a09bf997f.jpg" class="img-1 absolute inset-0 w-full h-full object-cover rounded-3xl" />

  <img src="https://i.pinimg.com/736x/1b/ab/9a/1bab9a520ddc07ab8b1a9b60e1afcfee.jpg" class="img-2 absolute inset-0 w-full h-full object-cover rounded-3xl" />

  <img src="https://i.pinimg.com/736x/5f/bf/31/5fbf311ba6d308b5dee2180fc3e414a6.jpg" class="img-3 absolute inset-0 w-full h-full object-cover rounded-3xl" />

  <img src="https://i.pinimg.com/736x/29/fc/bb/29fcbbdbc6b81449756e7647711e7c9b.jpg" class="img-4 absolute inset-0 w-full h-full object-cover rounded-3xl" />

</div>
    </div>

    <!-- Background Accent -->
    <div
      class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2
      w-[700px] h-[700px] rounded-full bg-white/5 blur-3xl"
    ></div>
  </section>
</template>
<style scoped></style>