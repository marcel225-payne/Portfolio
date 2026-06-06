<script setup>
import { GraduationCap, Calendar, CheckCircle2 } from 'lucide-vue-next';

const educationData = [
    {
        id: 1,
        institution: "Université polytechnique de Bingerville",
        degree: "Master en Informatique (MIAGE)",
        duration: "2022 - 2024",
        description: "Ingénierie de Projets Informatiques et Nouvelles Technologies. Acquisition de compétences stratégiques en gestion de projets et développement avancé."
    },
    {
        id: 2,
        institution: "Université polytechnique de Bingerville",
        degree: "Licence en Informatique (MIAGE)",
        duration: "2018 - 2021",
        description: "Formation solide en algorithmique, développement web et administration des bases de données."
    },
    {
        id: 3,
        institution: "College Moderne les Pingouins",
        degree: "Baccalauréat Scientifique (Série D)",
        duration: "2017 - 2018",
        description: "Obtention du diplôme de fin d'études secondaires avec une base solide en sciences et mathématiques."
    },
    {
        id: 4,
        institution: "NEURONNE TECHNOLOGY",
        degree: "Développement Web Front-end (Vue.js)",
        duration: "Mai - Juin 2026",
        description: "Formation intensive spécialisée sur Vue.js pour la création d'interfaces utilisateur modernes et réactives."
    }
];
</script>

<template>
    <section class="text-white py-24 bg-[#0f172a] overflow-hidden" id="education">
        <div class="max-w-7xl mx-auto px-6 lg:px-16">
            <div class="mb-20">
                <p class="text-amber-400 text-sm uppercase tracking-[0.2em] font-semibold mb-3">
                    Mon parcours éducatif
                </p>
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">
                    Education
                </h2>
            </div>
            
            <div class="flex flex-col lg:flex-row items-start gap-16">
                <!-- Image avec marge supérieure pour descendre l'emplacement -->
                <div class="w-full lg:w-5/12 flex justify-center lg:justify-start mt-55" data-aos="fade-right">
                    <div class="relative w-66 md:w-90">
                        <div class="absolute inset-0 translate-x-4 translate-y-4 rounded-2xl border border-amber-500/30 z-0"></div>
                        <div class="relative z-10 bg-[#1e293b] rounded-2xl overflow-hidden border border-[#1f1641]">
                            <img 
                                src="../assets/imageEduc.JPEG" 
                                alt="Education" 
                                class="w-full h-64 md:h-96 object-cover transform transition-transform duration-500 hover:scale-105">
                        </div>
                    </div>
                </div>

                <!-- Liste des formations -->
                <div class="w-full lg:w-7/12 space-y-6" data-aos="fade-left">
                    <div v-for="edu in educationData"
                        :key="edu.id"
                        class="group relative p-6 rounded-2xl bg-[#1e293b]/50 border border-transparent hover:border-amber-500/30 transition-all duration-300 hover:bg-[#1e293b]">
                        
                        <div class="flex flex-col sm:flex-row sm:items-start justify-between gap-4 mb-4">
                            <div class="flex items-start gap-4">
                                <div class="p-2 bg-[#0f172a] rounded-lg border border-amber-500/20 group-hover:border-amber-500 transition-colors">
                                    <GraduationCap class="text-amber-400" size="24"/>
                                </div>
                                <div class="flex-1">
                                    <h3 class="text-lg font-bold text-white group-hover:text-amber-400 transition-colors leading-snug">
                                        {{ edu.degree }}
                                    </h3>
                                    <p class="text-amber-500/70 text-sm font-medium mt-1">
                                        {{ edu.institution }}
                                    </p>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 text-xs font-medium bg-[#0f172a] px-3 py-1 rounded-full border border-amber-500/10 text-amber-400 whitespace-nowrap">
                                <Calendar size="12"/>
                                {{ edu.duration }}
                            </div>
                        </div>

                        <p class="text-gray-400 text-sm leading-relaxed mb-4 pl-12">
                            {{ edu.description }}
                        </p>

                        <div class="flex items-center gap-2 text-[10px] uppercase tracking-wider text-amber-500 font-bold pl-12">
                            <CheckCircle2 size="12"/>
                            Academic Excellence
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>