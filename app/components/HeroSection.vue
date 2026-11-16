<script setup lang="ts">
import { ArrowRight, BarChart3, Brain, Heart, Mic, Play, ShieldCheck, Stethoscope } from '@lucide/vue'

const featureItems = [
  { icon: Brain, title: 'AI Personalized Activities', text: 'Tailored to individual needs' },
  { icon: Mic, title: 'Multilingual Voice Assistant', text: 'Speak in your language' },
  { icon: BarChart3, title: 'Track Progress', text: 'Monitor improvement' },
  { icon: Stethoscope, title: 'Doctor Dashboard', text: 'Expert care & insights' },
  { icon: Heart, title: 'Better Quality of Life', text: 'A healthier, happier you' },
]
</script>

<template>
  <section class="relative isolate overflow-hidden bg-[#f7efff]" aria-labelledby="hero-heading">
    <div class="absolute inset-0 -z-10 bg-[radial-gradient(circle_at_72%_22%,rgba(255,255,255,0.92),transparent_34%),linear-gradient(112deg,#f8f1ff_0%,#f3eaff_52%,#eee1ff_100%)]" aria-hidden="true" />

    <div class="container-wide relative z-10 grid min-h-[520px] items-center pb-24 pt-0 sm:pt-0 lg:min-h-[535px] lg:grid-cols-[0.92fr_1.08fr] lg:gap-5 lg:pb-20 lg:pt-16">
      <div class="relative z-20 order-2 max-w-[620px] pt-10 lg:order-none lg:pb-6 lg:pt-0">
        <h1 id="hero-heading" class="font-display text-[3.2rem] font-extrabold leading-[0.98] tracking-[-0.055em] text-[#281166] sm:text-6xl lg:text-[4.15rem] xl:text-[4.55rem]">
          D4 Dementia
        </h1>
        <h2 class="mt-4 max-w-[570px] font-display text-xl font-extrabold leading-[1.18] text-[#2f176f] sm:text-2xl lg:text-[1.65rem]">
          Cognitive Care. Personalized Activities.<br class="hidden sm:block"> Connected Support.
        </h2>
        <p class="mt-5 max-w-[500px] text-base font-medium leading-7 text-[#413660] sm:text-lg sm:leading-8">
          An AI-powered platform to support memory, mental wellness and quality of life for people with Dementia.
        </p>

        <div class="mt-7 flex flex-col gap-3 sm:flex-row">
          <a href="#activities" class="focus-ring inline-flex min-h-14 items-center justify-center gap-3 rounded-full bg-[#6d2bc8] px-7 text-base font-bold text-white shadow-lg shadow-purple-300/60 transition hover:-translate-y-0.5 hover:bg-[#5520ad]">
            <Play class="h-5 w-5 fill-current" aria-hidden="true" />
            Get Started
            <ArrowRight class="h-5 w-5" aria-hidden="true" />
          </a>
          <a href="#about" class="focus-ring inline-flex min-h-14 items-center justify-center gap-3 rounded-full border-2 border-[#7042ad] bg-white/35 px-7 text-base font-bold text-[#3c207f] transition hover:bg-white/80">
            <span class="grid h-5 w-5 place-items-center rounded-full bg-[#3c207f] text-xs text-white" aria-hidden="true">i</span>
            Learn More
          </a>
        </div>

        <div class="mt-6 flex flex-wrap items-center gap-x-3 gap-y-2 text-sm font-bold text-[#3b315b]">
          <span class="inline-flex items-center gap-2"><ShieldCheck class="h-5 w-5 text-emerald-600" aria-hidden="true" /> Safe</span>
          <span aria-hidden="true">•</span>
          <span>Accessible</span>
          <span aria-hidden="true">•</span>
          <span>Multilingual</span>
        </div>
      </div>

      <div class="relative order-1 -mx-5 min-h-[285px] sm:-mx-8 sm:min-h-[390px] lg:order-none lg:absolute lg:bottom-0 lg:right-[-2.5rem] lg:mx-0 lg:mt-0 lg:h-[535px] lg:w-[calc(59%+2.5rem)]">
        <img
          src="/images/hero-caregiver.png"
          alt="A smiling older woman spending time with a caring healthcare professional"
          class="absolute inset-0 h-full w-full object-cover object-center translate-x-0 lg:translate-x-[18%]"
        >
        <div class="absolute inset-0 bg-gradient-to-r from-[#f7efff] via-[#f7efff]/10 to-transparent lg:w-[38%]" aria-hidden="true" />
      </div>
    </div>

    <div class="pointer-events-none absolute bottom-[-1px] left-[-2%] z-20 h-20 w-[104%] bg-white [clip-path:ellipse(58%_48%_at_50%_100%)] sm:h-24 lg:h-28" aria-hidden="true" />
    <div class="pointer-events-none absolute bottom-5 left-[-2%] z-20 h-16 w-[104%] bg-[#b988f2] [clip-path:ellipse(57%_45%_at_50%_100%)] sm:bottom-6 sm:h-20 lg:bottom-7 lg:h-24" aria-hidden="true" />
    <div class="pointer-events-none absolute bottom-0 left-[-2%] z-20 h-12 w-[104%] bg-white [clip-path:ellipse(55%_46%_at_50%_100%)] sm:h-16 lg:h-20" aria-hidden="true" />

    <div class="container-wide relative z-30 -mt-1 pb-8 lg:pb-10">
      <div class="flex snap-x snap-mandatory gap-0 overflow-x-auto rounded-[1.75rem] border border-purple-100 bg-[#fcf8ff] shadow-[0_15px_42px_rgba(83,39,168,0.12)] sm:grid sm:grid-cols-2 sm:overflow-hidden lg:grid-cols-5">
        <div v-for="(item, index) in featureItems" :key="item.title" class="flex min-w-[82%] snap-start items-center gap-3 border-r border-purple-200 px-5 py-5 last:border-r-0 sm:min-w-0 sm:border-b sm:px-6 lg:block lg:border-b-0 lg:border-r lg:last:border-r-0 lg:px-4 lg:py-5 lg:text-center">
          <span class="grid h-11 w-11 shrink-0 place-items-center rounded-2xl bg-[#efe3ff] text-[#5c24b0] lg:mx-auto">
            <component :is="item.icon" class="h-6 w-6" stroke-width="2.3" aria-hidden="true" />
          </span>
          <div class="mt-0 lg:mt-3">
            <h3 class="font-display text-sm font-extrabold leading-tight text-[#2b155e]">{{ item.title }}</h3>
            <p class="mt-1 text-xs leading-5 text-[#6c6182]">{{ item.text }}</p>
          </div>
          <span v-if="index < featureItems.length - 1" class="hidden" aria-hidden="true" />
        </div>
      </div>
    </div>
  </section>
</template>
