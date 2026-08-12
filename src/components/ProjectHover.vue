<script setup>
import { onMounted } from 'vue';
import gsap from 'gsap';
const projectImages = {
  building: 'https://images.unsplash.com/photo-1487958449943-2429e8be8625?w=800',

  garden: 'https://images.unsplash.com/photo-1558904541-efa843a96f01?w=800',

  fashion: 'https://images.unsplash.com/photo-1490481651871-ab68de25d43d?w=800',

  interior: 'https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=800'
}
onMounted(()=>{
  const projectItems = gsap.utils.toArray('.project-item')
  const projectImage = document.querySelector('.project-image')
  projectItems.forEach(Element=>
    Element.addEventListener('mouseenter',()=>{
     const project = Element.dataset.project
      console.log(project)
    })
  )
})
</script>
<template>
  <section class="min-h-screen bg-black text-white flex items-center justify-center">

   <div class="project-list flex flex-col gap-4">

  <div
    class="project-item text-6xl font-bold cursor-pointer"
    data-project="building"
  >
    Building
  </div>

  <div
    class="project-item text-6xl font-bold cursor-pointer"
    data-project="garden"
  >
    Garden
  </div>

  <div
    class="project-item text-6xl font-bold cursor-pointer"
    data-project="fashion"
  >
    Fashion
  </div>

  <div
    class="project-item text-6xl font-bold cursor-pointer"
    data-project="interior"
  >
    Interior
  </div>

</div>

    <div class="image-container ml-20 w-[300px] h-[400px]">

      <img
        class="project-image w-full h-full object-cover"
        src="https://images.unsplash.com/photo-1487958449943-2429e8be8625?w=800"
        alt="Project"
      >

    </div>

  </section>
</template>
<style scoped></style>