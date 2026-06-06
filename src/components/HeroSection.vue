<script setup>
import { Download } from 'lucide-vue-next';
</script>

<template>
    <section class="relative w-full py-24 overflow-hidden bg-[#0f172a]">
        
        <!-- Dégradés décoratifs en mode Or -->
        <div class="absolute top-0 right-0 w-[600px] h-[600px] bg-amber-500/10 blur-[120px] rounded-full pointer-events-none"></div>
        <div class="absolute bottom-0 left-0 w-[400px] h-[400px] bg-yellow-600/10 blur-[100px] rounded-full pointer-events-none"></div>

        <div class="w-full px-5 sm:px-8 md:px-12 lg:px-8 max-w-7xl mx-auto relative">
            <div class="grid lg:grid-cols-2 gap-16 xl:gap-24 items-center">
                
                <div class="space-y-8">
                    <h1 class="text-white font-extrabold text-5xl md:text-6xl lg:text-7xl leading-tight">
                        Bonjour, je suis <br/>
                        <!-- Dégradé Or -->
                        <span class="text-transparent bg-clip-text bg-gradient-to-r from-amber-400 via-yellow-500 to-amber-400 animate-gradient-x">
                            Thio Marcel
                        </span> 
                    </h1>
                    
                    <p class="text-lg text-gray-400 leading-relaxed max-w-xl">
                        Développeur web passionné par l'innovation. Je transforme des idées complexes en expériences numériques fluides, 
                        modernes et performantes.
                    </p>

                    <div class="flex flex-col sm:flex-row gap-4 pt-4">
                        <!-- Bouton Hire Me en Or -->
                        <button class="px-8 py-4 rounded-full bg-amber-500 hover:bg-amber-600 
                            text-black font-bold transition-all shadow-[0_0_20px_rgba(245,158,11,0.4)] hover:scale-105">
                            Hire Me
                        </button>

                        <!-- Bouton CV Or -->
                        <button class="px-8 py-4 rounded-full border border-amber-500/30 text-amber-400 hover:bg-amber-500/10 
                            hover:border-amber-500/50 transition-all flex items-center justify-center gap-2">
                            <Download :size="18"/>
                            <a href="/THIO_aej_cv.pdf" download="THIO_aej_cv.pdf" class="font-semibold">
                                Télécharger CV
                            </a>
                        </button>
                    </div>
                </div>

                <!-- Image avec bordure Or -->
                <div class="flex justify-center lg:justify-end items-center relative">
                    <div class="relative w-[340px] h-[340px] md:w-[450px] md:h-[450px]">
                        <div class="absolute inset-0 bg-gradient-to-tr from-amber-500 to-yellow-300 rounded-[40%_60%_70%_30%/40%_50%_60%_50%] opacity-20 blur-xl animate-pulse"></div>
                        
                        <div class="relative w-full h-full rounded-[40%_60%_70%_30%/40%_50%_60%_50%] shadow-2xl border-2 border-amber-500/20 overflow-hidden">
                            <img 
                                src="../assets/image.png" 
                                alt="Thio Marcel"
                                class="w-full h-full object-cover scale-105 hover:scale-100 transition-transform duration-700"
                            >
                        </div>
                    </div>
                </div> 
            </div> 
        </div>
    </section>
</template>

<style scoped>
.animate-gradient-x {
    background-size: 200% 200%;
    animation: gradient 5s ease infinite;
}
@keyframes gradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
</style>