<script setup>
import { Mail, Phone, Linkedin, MapPin } from 'lucide-vue-next';
import { reactive, ref } from 'vue';

const contactInfo = [
    {
        id: 1,
        icon: Mail,
        title: 'Email',
        value: 'thiomarcel54@gmail.com',
        link: 'mailto:thiomarcel54@gmail.com',
    },
    {
        id: 2,
        icon: Phone,
        title: 'Téléphone',
        value: '+225 0711350321',
        link: 'tel:+2250711350321',
    },
    {
        id: 3,
        icon: Linkedin,
        title: 'LinkedIn',
        value: 'linkedin.com/in/marcel-thio-a08659284',
        link: 'https://www.linkedin.com/in/marcel-thio-a08659284',
    },
    {
        id: 4,
        icon: MapPin,
        title: 'Localisation',
        value: 'Abidjan, CI',
        link: null,
    }
];

const formData = reactive({
    email: '',
    subject: '',
    message: '',
});

const isSubmitting = ref(false);

const handleSubmit = async () => {
    isSubmitting.value = true;
    try {
        // Simuler un envoi
        await new Promise(resolve => setTimeout(resolve, 1500));
        formData.email = '';
        formData.subject = '';
        formData.message = '';
        alert('Message envoyé avec succès !');
    } catch (error) {
        alert('Échec de l\'envoi. Veuillez réessayer.');
    } finally {
        isSubmitting.value = false;
    }
};
</script>

<template>
    <section class="py-24 bg-[#0f172a] text-white" id="contact">
        <div class="container mx-auto px-6 lg:px-16 max-w-6xl">
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-extrabold mb-4">
                    Contactez <span class="text-amber-400">Moi</span>
                </h2>
                <div class="w-24 h-1 bg-amber-500 mx-auto rounded-full"></div>
            </div>

            <div class="grid md:grid-cols-2 gap-12">
                <div>
                    <p class="text-gray-400 mb-8 leading-relaxed">
                        Passionné par l'innovation et le partage d'expériences, je suis toujours ouvert aux échanges constructifs. 
                        N'hésitez pas à me contacter pour discuter de projets, de partenariats ou simplement pour élargir notre réseau.
                    </p>
                    <div class="space-y-6">
                        <div v-for="info in contactInfo" :key="info.id" class="flex items-center gap-4 group">
                            <div class="w-12 h-12 rounded-xl bg-[#1e293b] flex items-center justify-center group-hover:bg-amber-500/20 
                            transition-colors border border-white/5">
                                <component :is="info.icon" :size="20" class="text-amber-400"/>
                            </div>
                            <div>
                                <h4 class="text-white font-medium text-sm">{{ info.title }}</h4>
                                <a v-if="info.link" :href="info.link" target="_blank" rel="noopener noreferrer"
                                   class="text-gray-400 text-sm hover:text-amber-400 transition-colors">
                                    {{ info.value }}
                                </a>
                                <p v-else class="text-gray-400 text-sm">{{ info.value }}</p>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="bg-[#1e293b] rounded-2xl p-8 border border-white/5">
                    <form @submit.prevent="handleSubmit">
                        <div class="mb-5">
                            <label class="block mb-2 text-sm font-medium">Email</label>
                            <input type="email" v-model="formData.email" required
                                   class="w-full px-4 py-3 bg-[#0f172a] border border-white/10 rounded-xl focus:border-amber-500 outline-none transition-all"
                                   placeholder="votre@email.com">
                        </div>
                        <div class="mb-5">
                            <label class="block mb-2 text-sm font-medium">Message</label>
                            <textarea v-model="formData.message" required rows="4"
                                      class="w-full px-4 py-3 bg-[#0f172a] border border-white/10 rounded-xl focus:border-amber-500 outline-none transition-all"
                                      placeholder="Parlez-moi de votre projet..."></textarea>
                        </div>
                        <button type="submit" :disabled="isSubmitting"
                                class="w-full py-3 bg-amber-500 hover:bg-amber-600 text-white rounded-xl font-bold transition-all disabled:opacity-50">
                            {{ isSubmitting ? 'Envoi en cours...' : 'Envoyer le message' }}
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>