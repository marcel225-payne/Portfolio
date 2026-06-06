<script setup>
// Chargement dynamique des images depuis le dossier assets
const images = import.meta.glob('../assets/*.{png,jpg,jpeg,JPEG}', { eager: true });

const projects = [
    {
        id: 1,
        image: '../assets/proje1.png',
        title: 'Platforme de travaille colaboratif',
        desc: 'Une plateforme qui permet de travaillé en ligne.',
        techg: ['React', 'Node.js', 'MongoDB']
    },
    {
        id: 2,
        image: '../assets/proje2.png',
        title: 'Portefeuille ',
        desc: 'Interface pour la presentation de mon cv.',
        techg: ['Vue.js', 'Node.js', 'JavaScript']
    },
    {
        id: 3,
        image: '../assets/proje3.png',
        title: 'Solution ',
        desc: 'Application de gestion performante.',
        techg: ['React', 'Node.js', 'MongoDB']
    },
];

const getImageUrl = (path) => {
    return images[path]?.default || images[path];
};
</script>

<template>
    <section class="py-24 bg-[#0f172a]" id="projects">
        <div class="container mx-auto px-6 lg:px-16 max-w-7xl">
            
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">
                    Mes <span class="text-amber-400">Projets</span>
                </h2>
                <div class="w-24 h-1 bg-amber-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div v-for="project in projects" :key="project.id" 
                     class="group bg-[#1e293b] rounded-2xl overflow-hidden border border-white/5 hover:border-amber-500/50 shadow-lg transition-all duration-300">
                    
                    <div class="overflow-hidden h-48">
                        <img :src="getImageUrl(project.image)" :alt="project.title" 
                             class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                    </div>
                    
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2 group-hover:text-amber-400 transition-colors">
                            {{ project.title }}
                        </h3>
                        <p class="text-gray-400 text-sm mb-4"> {{ project.desc }} </p>
                        
                        <div class="flex flex-wrap gap-2 mt-3">
                            <span v-for="(tech, idx) in project.techg" :key="idx"
                                class="text-xs px-3 py-1 bg-[#0f172a] text-amber-400 border border-amber-500/20 rounded-full">
                                {{ tech }}
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>