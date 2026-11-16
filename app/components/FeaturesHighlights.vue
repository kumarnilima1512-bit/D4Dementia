<script setup lang="ts">
import { BarChart3, Brain, Heart, Mic, Stethoscope } from '@lucide/vue'

const highlights = [
  {
    icon: Brain,
    title: 'AI-guided activities',
    description: 'Personalized prompts that meet each person at their own pace.',
    tone: 'bg-[#efe5ff] text-[#6b2cc8]',
  },
  {
    icon: Mic,
    title: 'Voice assistant',
    description: 'Simple spoken guidance for a more natural experience.',
    tone: 'bg-[#e3efff] text-[#3c79c6]',
  },
  {
    icon: BarChart3,
    title: 'Progress insights',
    description: 'Clear patterns that help families and care teams support progress.',
    tone: 'bg-[#e4f7df] text-[#4c9c57]',
  },
  {
    icon: Stethoscope,
    title: 'Connected doctors',
    description: 'The right care team sees the right information, securely.',
    tone: 'bg-[#fff0df] text-[#d17b35]',
  },
  {
    icon: Heart,
    title: 'Everyday wellbeing',
    description: 'Small, positive routines that help every day feel brighter.',
    tone: 'bg-[#ffe5f0] text-[#ce4d84]',
  },
]
</script>

<template>
  <section id="about" class="bg-white py-20 sm:py-24" aria-labelledby="highlights-heading">
    <div class="container-wide">
      <div class="mx-auto max-w-2xl text-center">
        <p class="section-eyebrow">One connected care experience</p>
        <h2 id="highlights-heading" class="text-3xl font-extrabold text-[#241052] sm:text-4xl">Support that goes beyond a screen.</h2>
        <p class="mt-4 text-lg leading-8 text-[#6c6383]">Thoughtful tools for patients, families, and professionals—designed to feel calm, clear, and encouraging.</p>
      </div>

      <div class="mt-12 grid gap-4 sm:grid-cols-2 lg:grid-cols-5">
        <article v-for="item in highlights" :key="item.title" class="group rounded-[1.75rem] border border-purple-100 bg-[#fcfaff] p-6 transition duration-300 hover:-translate-y-2 hover:border-purple-200 hover:shadow-xl hover:shadow-purple-100/70">
          <div :class="['grid h-14 w-14 place-items-center rounded-2xl transition duration-300 group-hover:scale-110', item.tone]">
            <component :is="item.icon" class="h-7 w-7" stroke-width="2.2" aria-hidden="true" />
          </div>
          <h3 class="mt-5 font-display text-lg font-extrabold leading-tight text-[#2B145C]">{{ item.title }}</h3>
          <p class="mt-3 text-sm leading-6 text-[#756b8a]">{{ item.description }}</p>
        </article>
      </div>
    </div>
  </section>
</template>
