<script setup>
import { Menu, X } from 'lucide-vue-next';
import { ref } from 'vue';

const isMenuOpen = ref(false)

const menuItems = [
    { name: 'Education', href: '#education' },
    { name: 'Certification', href: '#certification' },
    { name: 'A propos', href: '#apropos' },
    { name: 'Competences', href: '#competences' },
    { name: 'Projects', href: '#projects' },
]

const scrollToSection = (href) => {
    isMenuOpen.value = false
    const element = document.querySelector(href)
    if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
    }
}
</script>

<template>
    <header class="fixed top-0 w-full z-50 bg-[#0f172a]/80 backdrop-blur-md border-b border-amber-500/20">
        <div class="max-w-7xl mx-auto px-6 py-6 flex justify-between items-center">
            
            <div class="text-white text-2xl font-black cursor-pointer tracking-wider">
                PORTFOLIO<span class="text-amber-400">.</span>
            </div>
            
            <nav class="hidden md:flex items-center gap-10">
                <ul class="flex gap-8">
                    <li v-for="item in menuItems" :key="item.name">
                        <button @click="scrollToSection(item.href)"
                            class="text-gray-300 hover:text-amber-400 text-sm font-medium transition-colors">
                            {{ item.name }}
                        </button>
                    </li>
                </ul>
                <button @click="scrollToSection('#contact')"
                    class="bg-amber-500 hover:bg-amber-600 text-black px-6 py-2 rounded-full text-sm font-bold transition-all shadow-[0_0_15px_rgba(245,158,11,0.3)]">
                    Contactez-moi
                </button>
            </nav>
            
            <button class="md:hidden text-white hover:text-amber-400 transition-colors" @click="isMenuOpen = !isMenuOpen">
                <Menu v-if="!isMenuOpen" :size="28" />
                <X v-else :size="28" />
            </button>
        </div>

        <div v-if="isMenuOpen" class="fixed inset-0 bg-[#0f172a]/95 backdrop-blur-lg z-40 flex flex-col items-center justify-center gap-10 md:hidden">
            <button class="absolute top-8 right-6 text-white hover:text-amber-400" @click="isMenuOpen = false">
                <X :size="32" />
            </button>
            
            <ul class="flex flex-col items-center gap-8">
                <li v-for="item in menuItems" :key="item.name">
                    <button @click="scrollToSection(item.href)" 
                        class="text-white text-2xl font-bold hover:text-amber-400 transition-colors">
                        {{ item.name }}
                    </button>
                </li>
                <li class="pt-6">
                    <button @click="scrollToSection('#contact')" 
                        class="bg-amber-500 text-black px-10 py-4 rounded-full text-lg font-bold hover:scale-105 transition-all">
                        Contactez-moi
                    </button>
                </li>
            </ul>
        </div>
    </header>
</template>