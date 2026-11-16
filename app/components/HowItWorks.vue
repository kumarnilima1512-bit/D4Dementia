<script setup lang="ts">
import { ArrowRight, BarChart3, Gamepad2, Mic, UserRound } from '@lucide/vue'

const steps = [
  { number: '01', icon: UserRound, title: 'Create a profile', description: 'Set up a calm, personal starting point for care.' },
  { number: '02', icon: Gamepad2, title: 'Choose an activity', description: 'Pick from gentle games and guided routines.' },
  { number: '03', icon: Mic, title: 'Talk or tap', description: 'Use your voice or simple touch controls.' },
  { number: '04', icon: BarChart3, title: 'See progress', description: 'Share helpful insights with the care team.' },
]
</script>

<template>
  <section id="how-it-works" class="bg-white py-20 sm:py-24" aria-labelledby="how-heading">
    <div class="container-wide">
      <div class="mx-auto max-w-2xl text-center">
        <p class="section-eyebrow">A simple path forward</p>
        <h2 id="how-heading" class="text-3xl font-extrabold text-[#241052] sm:text-4xl">How it works</h2>
        <p class="mt-4 text-lg leading-8 text-[#6c6383]">Simple steps. Meaningful moments. A little more confidence each day.</p>
      </div>

      <div class="relative mt-14 grid gap-10 md:grid-cols-4 md:gap-6">
        <div class="absolute left-[12%] right-[12%] top-9 hidden h-px bg-purple-200 md:block" aria-hidden="true" />
        <article v-for="(step, index) in steps" :key="step.number" class="relative text-center">
          <div class="relative z-10 mx-auto grid h-[4.5rem] w-[4.5rem] place-items-center rounded-full border-8 border-white bg-[#eee1ff] text-purple-700 shadow-lg shadow-purple-100">
            <component :is="step.icon" class="h-7 w-7" stroke-width="2.2" aria-hidden="true" />
          </div>
          <p class="mt-5 text-xs font-extrabold uppercase tracking-[0.18em] text-purple-600">Step {{ step.number }}</p>
          <h3 class="mt-2 font-display text-lg font-extrabold text-[#2B145C]">{{ step.title }}</h3>
          <p class="mx-auto mt-2 max-w-[190px] text-sm leading-6 text-[#756b8a]">{{ step.description }}</p>
          <ArrowRight v-if="index < steps.length - 1" class="absolute -bottom-8 left-1/2 h-5 w-5 -translate-x-1/2 rotate-90 text-purple-300 md:-right-5 md:bottom-auto md:left-auto md:top-8 md:translate-x-0 md:rotate-0" aria-hidden="true" />
        </article>
      </div>
    </div>
  </section>
</template>
