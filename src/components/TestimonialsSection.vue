<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger  from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
    console.log("Mounted");
gsap.set('.img-2,.img-3,.img-4',{
  y:80,opacity:0
}
)
const tl = gsap.timeline({scrollTrigger:{
 trigger:'.story',start:'top top',end:'+=300%',pin:true,scrub:true,markers:true
}})
tl.to('.img-2',{
  y:0,opacity:1
})
.to('.step-title',{
  y:-50,duration:0.5,opacity:0
},'<')
.to('.step-desc',{
  y:-50,opacity:0,duration:0.5
},'<')
.to('.step-title',{
  textContent:'design',duration:0 ,y:50
})
.to('.step-desc',{
  y:50,duration:0,textContent:'We turn ideas into thoughtful designs that are beautiful, intuitive, and built around your users.'
})
.to('.step-title',{
  opacity:1,y:0,duration:0.4
},'<')
.to('.step-desc',{
  y:0,opacity:1,duration:0.4
},'<')
.to('.img-3',{
  y:0,opacity:1
})
.to('.step-title',{
  y:-50,duration:0.5,opacity:0
},'<')
.to('.step-desc',{
  y:-50,opacity:0,duration:0.5
},'<')
.to('.step-title',{
  textContent:'Develop',duration:0 ,y:50
})
.to('.step-desc',{
  y:50,duration:0,textContent:'We bring the design to life with clean, scalable code and smooth interactions that feel effortless.'
})
.to('.step-title',{
  opacity:1,y:0,duration:0.4
},'<')
.to('.step-desc',{
  y:0,opacity:1,duration:0.4
},'<')
.to('.img-4',{
  y:0,opacity:1
})
.to('.step-title',{
  y:-50,duration:0.5,opacity:0
},'<')
.to('.step-desc',{
  y:-50,opacity:0,duration:0.5
},'<')
.to('.step-title',{
  textContent:'Launch',duration:0 ,y:50
})
.to('.step-desc',{
  y:50,duration:0,textContent:"We polish every detail, test the experience, and launch your product ready to make an impact."

})
.to('.step-title',{
  opacity:1,y:0,duration:0.4
},'<')
.to('.step-desc',{
  y:0,opacity:1,duration:0.4
},'<')
})
</script>
<template>
  <!-- Story Section -->
  <section
    class="story relative h-screen bg-[#0d0d0d] text-white flex items-center overflow-hidden px-16"
  >
    <!-- Left Content -->
    <div class="w-1/2 z-10">
      <p class="uppercase tracking-[0.35em] text-sm text-gray-400 mb-4">
        Our Process
      </p>

      <div class="overflow-none">
        <h2 class="step-title text-7xl font-bold leading-none">
          Discover
        </h2>
      </div>

      <div class="overflow-hidden mt-6">
        <p class="step-desc max-w-lg text-lg text-gray-400 leading-relaxed">
          We dive deep into your brand, audience, and goals to understand
          exactly what needs to be built.
        </p>
      </div>

      <button
        class="mt-10 px-6 py-3 border border-white/20 rounded-full hover:bg-white hover:text-black transition-all duration-300"
      >
        Learn More
      </button>
    </div>

    <!-- Right Images -->
    <div class="w-1/2 flex justify-center items-center">
      <div class="relative w-[650px] h-[450px]">

        <img
          class="img-1 absolute inset-0 w-full h-full object-cover rounded-3xl"
          src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=1200"
        />

        <img
          class="img-2 absolute inset-0 w-full h-full object-cover rounded-3xl"
          src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?w=1200"
        />

        <img
          class="img-3 absolute inset-0 w-full h-full object-cover rounded-3xl"
          src="https://images.unsplash.com/photo-1551434678-e076c223a692?w=1200"
        />

        <img
          class="img-4 absolute inset-0 w-full h-full object-cover rounded-3xl"
          src="https://images.unsplash.com/photo-1521737604893-d14cc237f11d?w=1200"
        />

      </div>
    </div>

    <!-- Background Blur -->
    <div
      class="absolute w-[700px] h-[700px] rounded-full bg-white/5 blur-3xl top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
    ></div>
  </section>

  <!-- Dummy Next Section -->
  <section
    class="h-screen bg-white flex items-center justify-center"
  >
    <h2 class="text-6xl font-bold text-black">
      Next Section
    </h2>
  </section>
</template>
<style scoped></style>