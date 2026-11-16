<script setup lang="ts">
import { ArrowRight, Brain, MessageCircle, Puzzle, Target } from '@lucide/vue'

const activities = [
  {
    icon: Brain,
    title: 'Memory games',
    description: 'Recall and remember',
    color: 'bg-[#efe4ff]',
    iconColor: 'text-[#713bc3]',
    accent: 'from-[#b99af4] to-[#7438c3]',
  },
  {
    icon: Target,
    title: 'Attention tasks',
    description: 'Focus and concentrate',
    color: 'bg-[#e0edff]',
    iconColor: 'text-[#3a77c5]',
    accent: 'from-[#86b9ee] to-[#4274c8]',
  },
  {
    icon: MessageCircle,
    title: 'Language practice',
    description: 'Speak and understand',
    color: 'bg-[#e5f8df]',
    iconColor: 'text-[#4f9a57]',
    accent: 'from-[#9bd78f] to-[#54a05c]',
  },
  {
    icon: Puzzle,
    title: 'Problem solving',
    description: 'Think and decide',
    color: 'bg-[#fff0df]',
    iconColor: 'text-[#d57c3f]',
    accent: 'from-[#f3b77d] to-[#dc7c42]',
  },
]
</script>

<template>
  <section id="activities" class="bg-[#fbf8ff] py-20 sm:py-24" aria-labelledby="activities-heading">
    <div class="container-wide">
      <div class="mx-auto max-w-2xl text-center">
        <p class="section-eyebrow">Made to feel rewarding</p>
        <h2 id="activities-heading" class="text-3xl font-extrabold text-[#241052] sm:text-4xl">Cognitive activities</h2>
        <p class="mt-4 text-lg leading-8 text-[#6c6383]">Engaging, easy-to-use activities that keep the mind active without adding pressure.</p>
      </div>

      <div class="mt-12 grid gap-5 sm:grid-cols-2 lg:grid-cols-4">
        <article v-for="activity in activities" :key="activity.title" :class="['group relative overflow-hidden rounded-[1.75rem] p-7 text-center shadow-sm transition duration-300 hover:-translate-y-2 hover:shadow-xl', activity.color]">
          <div :class="['mx-auto grid h-20 w-20 place-items-center rounded-[1.5rem] bg-white/75 shadow-sm transition duration-300 group-hover:rotate-3 group-hover:scale-105', activity.iconColor]">
            <component :is="activity.icon" class="h-10 w-10" stroke-width="1.8" aria-hidden="true" />
          </div>
          <h3 class="mt-6 font-display text-xl font-extrabold text-[#2B145C]">{{ activity.title }}</h3>
          <p class="mt-2 text-sm font-medium text-[#665a7f]">{{ activity.description }}</p>
          <a href="#contact" class="focus-ring mt-6 inline-flex min-h-11 items-center gap-2 rounded-full bg-[#6b2cc8] px-5 text-sm font-bold text-white shadow-md shadow-purple-200 transition hover:bg-[#5520ad]">
            Try it now
            <ArrowRight class="h-4 w-4" aria-hidden="true" />
          </a>
          <div :class="['absolute -bottom-12 -right-12 h-28 w-28 rounded-full bg-gradient-to-br opacity-20 blur-2xl', activity.accent]" aria-hidden="true" />
        </article>
      </div>
    </div>
  </section>
</template>
