<script setup lang="ts">
import { ChevronDown, Gamepad2, Globe2, Info, Mail, Menu, Settings2, UserRound, X } from '@lucide/vue'

const isMenuOpen = ref(false)
const selectedLanguage = ref('EN')

const navItems = [
  { label: 'Home', href: '#top', icon: 'home' },
  { label: 'About', href: '#about', icon: Info },
  { label: 'Activities', href: '#activities', icon: Gamepad2 },
  { label: 'How It Works', href: '#how-it-works', icon: Settings2 },
  { label: 'Contact', href: '#contact', icon: Mail },
]

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <header id="top" class="relative z-50 border-b border-purple-100/80 bg-[#fbf7ff]/95 backdrop-blur-xl">
    <div class="container-wide flex min-h-[76px] items-center justify-between gap-6">
      <BrandLogo />

      <nav class="hidden items-center gap-1 xl:flex" aria-label="Primary navigation">
        <a
          v-for="item in navItems"
          :key="item.label"
          :href="item.href"
          class="focus-ring inline-flex min-h-11 items-center gap-2 rounded-full px-4 text-sm font-bold text-[#2B145C] transition hover:bg-purple-100 hover:text-purple-700"
          :class="item.label === 'Home' ? 'bg-purple-600 text-white shadow-lg shadow-purple-200 hover:bg-purple-700 hover:text-white' : ''"
        >
          <span v-if="item.icon === 'home'" class="grid h-5 w-5 place-items-center" aria-hidden="true">⌂</span>
          <component :is="item.icon" v-else class="h-4 w-4" stroke-width="2.5" aria-hidden="true" />
          {{ item.label }}
        </a>
      </nav>

      <div class="hidden items-center gap-3 xl:flex">
        <label class="focus-within:ring-4 focus-within:ring-purple-100 flex min-h-11 items-center gap-1 rounded-full border border-purple-200 bg-white px-3 text-sm font-bold text-[#2B145C]">
          <Globe2 class="h-4 w-4 text-purple-600" aria-hidden="true" />
          <span class="sr-only">Choose language</span>
          <select v-model="selectedLanguage" class="cursor-pointer appearance-none bg-transparent pr-1 outline-none" aria-label="Choose language">
            <option>EN</option>
            <option>BN</option>
            <option>HI</option>
          </select>
          <ChevronDown class="h-4 w-4 text-purple-500" aria-hidden="true" />
        </label>
        <a href="#contact" class="focus-ring inline-flex min-h-11 items-center gap-2 rounded-full bg-[#6b2cc8] px-6 text-sm font-bold text-white shadow-lg shadow-purple-200 transition hover:-translate-y-0.5 hover:bg-[#5520ad]">
          <UserRound class="h-4 w-4" aria-hidden="true" />
          Login
        </a>
      </div>

      <button
        type="button"
        class="focus-ring grid h-12 w-12 place-items-center rounded-2xl border border-purple-200 bg-white text-[#2B145C] xl:hidden"
        :aria-expanded="isMenuOpen"
        aria-controls="mobile-navigation"
        aria-label="Toggle navigation"
        @click="isMenuOpen = !isMenuOpen"
      >
        <X v-if="isMenuOpen" class="h-6 w-6" aria-hidden="true" />
        <Menu v-else class="h-6 w-6" aria-hidden="true" />
      </button>
    </div>

    <div v-if="isMenuOpen" id="mobile-navigation" class="border-t border-purple-100 bg-[#fbf7ff] px-5 py-5 xl:hidden">
      <nav class="container-wide flex flex-col gap-2" aria-label="Mobile navigation">
        <a
          v-for="item in navItems"
          :key="item.label"
          :href="item.href"
          class="focus-ring flex min-h-12 items-center gap-3 rounded-2xl px-4 text-base font-bold text-[#2B145C] transition hover:bg-purple-100"
          @click="closeMenu"
        >
          <span v-if="item.icon === 'home'" class="grid h-6 w-6 place-items-center" aria-hidden="true">⌂</span>
          <component :is="item.icon" v-else class="h-5 w-5 text-purple-600" stroke-width="2.5" aria-hidden="true" />
          {{ item.label }}
        </a>
        <div class="mt-3 flex flex-col gap-3 border-t border-purple-100 pt-4 sm:flex-row">
          <label class="flex min-h-12 flex-1 items-center justify-center gap-2 rounded-2xl border border-purple-200 bg-white px-4 text-sm font-bold text-[#2B145C]">
            <Globe2 class="h-5 w-5 text-purple-600" aria-hidden="true" />
            <span class="sr-only">Choose language</span>
            <select v-model="selectedLanguage" class="flex-1 bg-transparent outline-none" aria-label="Choose language">
              <option>EN</option>
              <option>BN</option>
              <option>HI</option>
            </select>
            <ChevronDown class="h-4 w-4 text-purple-500" aria-hidden="true" />
          </label>
          <a href="#contact" class="focus-ring inline-flex min-h-12 flex-1 items-center justify-center gap-2 rounded-2xl bg-[#6b2cc8] px-6 text-sm font-bold text-white" @click="closeMenu">
            <UserRound class="h-5 w-5" aria-hidden="true" />
            Login
          </a>
        </div>
      </nav>
    </div>
  </header>
</template>
