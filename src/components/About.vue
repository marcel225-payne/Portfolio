<script setup>
const stats = [
  { label: 'Projets', value: '+3' },
  { label: 'Années', value: '5' },
  { label: 'Clients', value: '+15' },
];
</script>

<template>
    <section class="text-white py-24 bg-[#0f172a] overflow-hidden" id="apropos">
        <div class="max-w-7xl mx-auto px-6 lg:px-16 grid md:grid-cols-2 gap-12 items-center">
            
            <!-- Texte -->
            <div data-aos="fade-right">
                <h2 class="text-4xl md:text-5xl font-extrabold text-white mb-6">
                    Apprendre plus <span class="text-amber-400">de Moi</span>
                </h2>
                <p class="text-gray-400 text-base lg:text-lg mb-10 leading-relaxed">
                    Développeur web passionné, je me spécialise dans la création d'expériences numériques dynamiques et réactives. 
                    Grâce à ma maîtrise des technologies modernes, je transforme vos idées en solutions performantes, tout en veillant à une interface utilisateur fluide et esthétique.
                </p>
                
                <!-- Statistiques -->
                <div class="grid grid-cols-3 max-w-xl gap-6">
                    <div v-for="item in stats" :key="item.label" 
                        class="text-center rounded-2xl bg-[#1e293b]/50 border border-white/5 p-5 transition-all duration-300 hover:border-amber-500/50 hover:bg-[#1e293b]">
                        <h3 class="text-2xl font-bold text-amber-400 md:text-3xl">{{ item.value }}</h3>
                        <p class="text-gray-400 text-xs uppercase tracking-wider mt-1">{{ item.label }}</p>
                    </div> 
                </div>
            </div>

            <!-- Image en forme organique (curviligne) -->
            <div class="flex justify-center lg:justify-end relative" data-aos="fade-left">
                <div class="relative w-72 h-96 md:w-80 md:h-[450px]">
                    <!-- Cadre organique de fond (décalé pour le relief) -->
                    <div class="absolute inset-0 z-0 border-2 border-amber-500/20 translate-x-5 translate-y-5 rounded-[40%_60%_70%_30%/40%_50%_60%_50%]"></div>
                    
                    <!-- Cadre principal -->
                    <div class="relative z-10 w-full h-full bg-[#1e293b] rounded-[40%_60%_70%_30%/40%_50%_60%_50%] overflow-hidden border-2 border-amber-500/30 shadow-2xl">
                        <img 
                            src="../assets/image2.png" 
                            alt="A propos de moi" 
                            class="w-full h-full object-cover object-center transition-transform duration-700 hover:scale-105"
                        >
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>