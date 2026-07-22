<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'

onMounted(() => {

})
</script>

<template>

  <section class="h-screen bg-[#0d0d0d] flex items-center justify-center">

    <div class="strip-container w-[700px] h-[500px] flex overflow-hidden">
<div class="strip strip-1"></div>
<div class="strip strip-2"></div>
<div class="strip strip-3"></div>
<div class="strip strip-4"></div>
<div class="strip strip-5"></div>

    </div>

  </section>

</template>

<style scoped>

.strip {
  width: 20%;
  height: 100%;
  background-image: url("https://images.unsplash.com/photo-1497366754035-f200968a6e72?w=1200");
  background-size: 500% 100%;
}

.strip-1{
    background-position: 0% 0%;
}
.strip-2{
    background-position: 25% 0%;
}
.strip-3{
    background-position: 50% 0%;
}
.strip-4{
    background-position: 75% 0%;
}
.strip-5{
    background-position: 100% 0%;
}
</style>