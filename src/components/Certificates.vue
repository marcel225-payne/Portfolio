<script setup>
import { Award, ShieldCheck, ExternalLink } from "lucide-vue-next"; 

const certifications = [
    {
        id: 1,
        title: "Formation en Vue.js",
        issuer: "Neurone Technology",
        date: "2026",
        link: "#",
        description: "Formation complète sur Vue.js pour la création d'applications web modernes et réactives."
    },
    {
        id: 2,
        title: "Certificat de compétence en BOOTSTRAP",
        issuer: "OpenClassrooms",
        date: "2023",
        link: "#",
        description: "Certification attestant des compétences en Bootstrap pour la création d'interfaces utilisateur modernes et réactives."
    },
    {
        id: 3,
        title: "Certificat de compétence en HTML5 et CSS3",
        issuer: "OpenClassrooms",
        date: "2022",
        link: "#",
        description: "Certification attestant des compétences en HTML5 et CSS3 pour la création de sites web modernes et responsives."
    }
];
</script>

<template>
    <section class="text-white py-24 bg-[#0f172a]" id="certification">
        <div class="max-w-7xl mx-auto px-6 lg:px-16">
            <div class="mb-16">
                <p class="text-amber-400 text-sm uppercase tracking-[0.2em] font-semibold mb-3">
                    Mes acquis
                </p>
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">
                    Certifications
                </h2>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div v-for="cert in certifications"
                    :key="cert.id"
                    class="group relative bg-[#1e293b]/50 border border-white/5 p-8 rounded-2xl transition-all duration-300 hover:border-amber-500/30 hover:bg-[#1e293b] hover:shadow-2xl">
                    
                    <!-- Icône Award -->
                    <div class="absolute -top-4 -right-4 bg-amber-500 p-3 rounded-xl shadow-[0_0_15px_rgba(245,158,11,0.4)] transform group-hover:rotate-12 transition-transform">
                        <Award class="text-white" size="24" />
                    </div>

                    <!-- Émetteur -->
                    <div class="flex items-center gap-2 mb-6 text-xs text-amber-400 font-bold">
                        <ShieldCheck size="16" />
                        {{ cert.issuer }}
                    </div>

                    <!-- Titre -->
                    <h3 class="text-xl font-bold mb-4 group-hover:text-amber-400 transition-colors">
                        {{ cert.title }}
                    </h3>

                    <!-- Description -->
                    <p class="text-sm text-gray-400 mb-8 leading-relaxed line-clamp-3">
                        {{ cert.description }}
                    </p>

                    <!-- Lien -->
                    <a :href="cert.link" 
                        target="_blank" 
                        rel="noopener noreferrer"
                        class="inline-flex items-center gap-2 text-sm font-semibold text-white hover:text-amber-400 transition-colors 
                        border-b border-white/10 hover:border-amber-500 pb-1">
                        Voir Certificat <ExternalLink size="14" />
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>