<script setup>
import { nextTick, onMounted, ref } from 'vue';
import gsap from 'gsap';
const activeImage = ref('building')
const projectImages = {
  building: [
    'https://images.unsplash.com/photo-1487958449943-2429e8be8625?w=800',
    'https://images.unsplash.com/photo-1511818966892-d7d671e672a2?w=800',
    'https://images.unsplash.com/photo-1497366811353-6870744d04b2?w=800'
  ],

  garden: [
    'https://images.unsplash.com/photo-1558904541-efa843a96f01?w=800',
    'https://images.unsplash.com/photo-1558521958-0a228e77e984?w=800',
    'https://images.unsplash.com/photo-1598902108854-10e335adac99?w=800'
  ],

  fashion: [
    'https://images.unsplash.com/photo-1490481651871-ab68de25d43d?w=800',
    'https://images.unsplash.com/photo-1483985988355-763728e1935b?w=800',
    'https://images.unsplash.com/photo-1529139574466-a303027c1d8b?w=800'
  ],

  interior: [
    'https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=800',
    'https://images.unsplash.com/photo-1497366216548-37526070297c?w=800',
    'https://images.unsplash.com/photo-1497366811353-6870744d04b2?w=800'
  ]
}
const showImages = async (project) => {
  activeImage.value = project

  await nextTick()

  const images = document.querySelectorAll('.project-image')

  gsap.fromTo(
    images,
    {
      opacity: 0,
      scale: 0.5,
      x: 0,
      y: 30
    },
    {
      opacity: 1,
      scale: 1,
      x: (index) => {
        if (index === 0) return -40
        if (index === 1) return 0
        return 40
      },
      y: (index) => {
        if (index === 0) return 20
        if (index === 1) return -20
        return 30
      },
      duration: 0.7,
      stagger: 0.1,
      ease: 'back.out(1.5)'
    }
  )
}
// onMounted(()=>{
//   const projectItems = gsap.utils.toArray('.project-item')
//   const projectImage = document.querySelector('.project-image')
//   projectItems.forEach(Element=>{
//     Element.addEventListener('mouseenter',()=>{
//      const project = Element.dataset.project
//      projectImage.src = projectImages[project]
//      gsap.fromTo(projectImage,{
// opacity:0,scale:0.7,y:40
//      },{
//         opacity: 1,
//     scale: 1,
//     y: 0,
//     duration: 0.6,
//     ease: 'back.out(1.7)',overwrite:'auto'
//      })
//     }) ,
//   Element.addEventListener('mouseleave',()=>{
//     gsap.to(projectImage,{
//       opacity:0, scale: 0.7,
//     y: 40,
//     duration: 0.3,
//     ease: 'power2.in',
//     overwrite: 'auto'
//     })
//   })
// })
  
// })
</script>
<template>
  <section class="min-h-screen bg-black text-white flex items-center justify-start">

   <div class="project-list flex flex-col gap-4">

  <div
  class="project-item text-6xl font-bold cursor-pointer"
  @mouseenter="showImages('building')"
>
  Building
</div>

<div
  class="project-item text-6xl font-bold cursor-pointer"
  @mouseenter="showImages('garden')"
>
  Garden
</div>

<div
  class="project-item text-6xl font-bold cursor-pointer"
  @mouseenter="showImages('fashion')"
>
  Fashion
</div>

<div
  class="project-item text-6xl font-bold cursor-pointer"
  @mouseenter="showImages('interior')"
>
  Interior
</div>


</div>
<div v-if="activeImage" class="flex" >
    <div  class="image-container flex ml-20  h-[400px] w-[340px]">

      <img
      v-for="(image, index) in projectImages[activeImage]"
  :key="image"
  :src="image"
  :class="['project-image w-full h-full object-cover',`image-${index}`]"
      >

    </div>
</div>
  </section>
</template>
<style scoped>
.image-container {
  position: relative;
  width: 340px;
  height: 450px;
}

.image-0 {
  left: 0;
  top: 40px;
}

.image-1 {
  left: 170px;
  top: 0;
}

.image-2 {
  left: 340px;
  top: 70px;
}
</style>