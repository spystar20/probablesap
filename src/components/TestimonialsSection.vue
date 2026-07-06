<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'


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

      <div class="overflow-hidden">
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