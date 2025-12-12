<template>
  <Header />
  <HeroSection />
  <About />
  <ProgramSection />
  <SpeakersSection />
  <Map />
  <SponsorsSection />
  <FAQ />
  <FooterSection />
</template>

<script setup>
/*
@review
Я бы здесь сделал компонент обертку Layout.vue
и разместил бы его в src/layouts
и в нем бы уже сделал импорт всех этих компонентов
Так будет проще делать адаптив
 */
import HeroSection from './sections/HeroSection.vue'
import About from './sections/About.vue'
import ProgramSection from './sections/ProgramSection.vue'
import Header from './sections/Header.vue'
import SpeakersSection from './sections/SpeakersSection.vue'
import FAQ from './sections/FAQ.vue'
import Map from './sections/Map.vue'
import SponsorsSection from './sections/SponsorsSection.vue'
import FooterSection from './sections/FooterSection.vue'
</script>
