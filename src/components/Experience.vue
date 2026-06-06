<script setup>
import { Briefcase, Building2, Calendar, Cpu, Layout } from 'lucide-vue-next';

const skills = [
    { id: 1, name: 'React Js', width: '85%', icons: Layout },
    { id: 2, name: 'Vue Js', width: '75%', icons: Cpu },
    { id: 3, name: 'JavaScript', width: '55%', icons: Layout },
    { id: 4, name: 'Figma', width: '75%', icons: Cpu },
];

const experiences = [
    {
        id: 1,
        role: 'Développeur',
        company: 'Université Polytechnique de Bingerville',
        date: 'Juillet 2021 - Janvier 2022'
    },
    {
        id: 2,
        role: 'Chef de Projet',
        company: 'Université Polytechnique de Bingerville',
        date: 'Juillet 2024 - Janvier 2025'
    }
];
</script>

<template>
    <section class="text-white py-24 bg-[#0f172a] relative overflow-hidden" id="skills">
        <div class="max-w-7xl mx-auto px-6 lg:px-16 relative z-10">
            <div class="grid md:grid-cols-2 gap-16 items-start">
                
                <!-- Skills -->
                <div data-aos="fade-right">
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                        Compétences <span class="text-amber-400">Techniques</span>
                    </h2>
                    <div class="space-y-8">
                        <div v-for="skill in skills" :key="skill.id" class="group">
                            <div class="flex items-center justify-between mb-2">
                                <div class="flex items-center gap-3">
                                    <div class="p-2 bg-[#1e293b] rounded-lg group-hover:bg-amber-500 transition-colors duration-300">
                                        <component :is="skill.icons" :size="20" class="text-amber-400 group-hover:text-white"/>
                                    </div>
                                    <span class="font-medium tracking-wide">{{ skill.name }}</span>
                                </div>
                                <span class="text-amber-400 font-bold">{{ skill.width }}</span>
                            </div>
                            
                            <div class="h-2 w-full bg-[#1e293b] rounded-full p-0.5 overflow-hidden">
                                <div class="h-full rounded-full bg-gradient-to-r from-amber-500 to-amber-300 shadow-[0_0_10px_rgba(245,158,11,0.5)] transition-all duration-1000 ease-out" 
                                     :style="{ width: skill.width }">
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Expériences -->
                <div data-aos="fade-left">
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                        <span>Expériences</span>
                    </h2>
                    <div class="space-y-6">
                        <div v-for="exp in experiences" :key="exp.id"
                            class="group relative p-6 rounded-2xl bg-[#1e293b]/50 border border-white/5 hover:border-amber-500/30 transition-all duration-300">
                            <div class="flex gap-4">
                                <div class="shrink-0 mt-1">
                                    <div class="p-3 bg-[#0f172a] rounded-xl border border-white/10 group-hover:border-amber-500 transition-colors">
                                        <Briefcase class="text-amber-400" size="24"/>
                                    </div>
                                </div>
                                <div class="grow">
                                    <h3 class="text-xl font-bold text-white group-hover:text-amber-400 transition-colors">
                                        {{ exp.role }}
                                    </h3>
                                    <div class="flex flex-col sm:flex-row sm:items-center gap-2 sm:gap-4 text-sm text-gray-400 mt-2">
                                        <span class="flex items-center gap-1.5">
                                            <Building2 size="14" class="text-amber-500"/>
                                            {{ exp.company }}
                                        </span>
                                        <span class="flex items-center gap-1.5">
                                            <Calendar size="14" class="text-amber-500"/>
                                            {{ exp.date }}
                                        </span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>