<script setup lang="ts">
import { ArrowRight, Heart, Sparkles } from '@lucide/vue'
</script>

<template>
  <section id="contact" class="px-5 pb-20 sm:px-8 sm:pb-24" aria-labelledby="cta-heading">
    <div class="container-wide">
      <div class="relative overflow-hidden rounded-[2.25rem] bg-gradient-to-br from-[#e8d6ff] via-[#f0e6ff] to-[#d8c1fa] px-7 py-10 shadow-[0_18px_50px_rgba(83,39,168,0.13)] sm:px-12 sm:py-12 lg:px-16">
        <div class="absolute -right-12 -top-16 h-48 w-48 rounded-full bg-white/50 blur-2xl" aria-hidden="true" />
        <div class="absolute -bottom-16 left-20 h-44 w-44 rounded-full bg-purple-300/40 blur-2xl" aria-hidden="true" />
        <div class="relative flex flex-col items-start justify-between gap-8 lg:flex-row lg:items-center">
          <div class="max-w-2xl">
            <span class="mb-4 inline-flex h-12 w-12 items-center justify-center rounded-2xl bg-white/80 text-purple-700 shadow-sm" aria-hidden="true">
              <Heart class="h-6 w-6 fill-current" />
            </span>
            <p class="section-eyebrow border-purple-300 bg-white/60">A brighter routine starts here</p>
            <h2 id="cta-heading" class="max-w-xl text-3xl font-extrabold text-[#2B145C] sm:text-4xl">Together, let’s make every day feel a little brighter.</h2>
            <p class="mt-4 max-w-xl text-base leading-7 text-[#5d5276] sm:text-lg">Explore a kinder way to support memory, connection, and wellbeing.</p>
          </div>
          <div class="flex w-full shrink-0 flex-col gap-3 sm:w-auto sm:flex-row lg:flex-col">
            <a href="#activities" class="focus-ring inline-flex min-h-14 items-center justify-center gap-3 rounded-full bg-[#6b2cc8] px-7 text-base font-bold text-white shadow-lg shadow-purple-200 transition hover:-translate-y-1 hover:bg-[#5520ad]">
              Get started
              <ArrowRight class="h-5 w-5" aria-hidden="true" />
            </a>
            <a href="#about" class="focus-ring inline-flex min-h-14 items-center justify-center gap-3 rounded-full border-2 border-purple-300 bg-white/70 px-7 text-base font-bold text-[#4a2198] transition hover:bg-white">
              <Sparkles class="h-5 w-5" aria-hidden="true" />
              Learn more
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
