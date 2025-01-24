<script setup>
import { ref } from 'vue'
import { Link , Head} from '@inertiajs/vue3'
import AuthLayout from '@/Layouts/AuthLayout.vue';
import {
  HomeIcon,
  WrenchIcon,
  ClockIcon,
  UserIcon,
  ArrowLeftIcon,
  MagnifyingGlassIcon,
} from '@heroicons/vue/24/outline'
import '@fortawesome/fontawesome-free/css/all.css';



const searchQuery = ref('')

const services = [
  {
    icon: WrenchIcon,
    name: "Bricolage",
    desc: "Petites réparations et installations"
  },
  {
    icon: ClockIcon,
    name: "Repassage",
    desc: "Service de repassage à domicile"
  },
  {
    icon: UserIcon,
    name: "Babysitting",
    desc: "Garde d'enfants qualifiée"
  },
  {
    icon: ArrowLeftIcon,
    name: "Déménagement",
    desc: "Service de déménagement"
  },
  {
    icon: ArrowLeftIcon,
    name: "Jardinage",
    desc: "Service de jardinage"
  },

]

const steps = [
  {
    step: "1",
    title: "Recherchez",
    desc: "Trouvez le service dont vous avez besoin"
  },
  {
    step: "2",
    title: "Réservez",
    desc: "Choisissez votre créneau et réservez en ligne"
  },
  {
    step: "3",
    title: "Profitez",
    desc: "Profitez de votre service en toute sérénité"
  }
]

const search = () => {
  // Implémentez la logique de recherche ici
  console.log('Recherche:', searchQuery.value)
}
</script>

<!-- resources/js/Pages/Home.vue -->
<template>
    <div class="min-h-screen bg-gray-50">
      <!-- Navigation -->
      <AuthLayout>
        <div class="bg-indigo-50 py-16">
              <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                  <h1 class="text-4xl font-bold text-gray-900 mb-4">
                    Trouvez le prestataire idéal pour vos services domestiques
                  </h1>
                  <p class="text-xl text-gray-600 mb-8">
                    Repassage, jardinage, menuiserie, babysitting et plus encore !
                  </p>
                  <div class="max-w-xl mx-auto">
                    <div class="flex bg-white rounded-lg shadow-lg p-2">
                      <MagnifyingGlassIcon class="h-6 w-6 text-gray-400 mx-2" />
                      <input
                        type="text"
                        placeholder="Quel service recherchez-vous ?"
                        class="flex-1 outline-none"
                        v-model="searchQuery"
                      />
                      <button
                        class="bg-indigo-600 text-white px-6 py-2 rounded-md"
                        @click="search"
                      >
                        Rechercher
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- Services Categories -->
            <div class="py-16">
              <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-3xl font-bold text-gray-900 mb-8 text-center">
                  Nos services
                </h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                  <div
                    v-for="(service, index) in services"
                    :key="index"
                    class="bg-white rounded-xl shadow-md p-6 hover:shadow-lg transition-shadow"
                  >
                    <component
                      :is="service.icon"
                      class="h-12 w-12 text-indigo-600 mb-4"
                    />
                    <h3 class="text-xl font-semibold text-gray-900 mb-2">{{ service.name }}</h3>
                    <p class="text-gray-600">{{ service.desc }}</p>
                  </div>
                </div>
              </div>
            </div>
                        <!-- How it works -->
                        <div class="bg-gray-100 py-16">
              <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-3xl font-bold text-gray-900 mb-8 text-center">
                  Comment ça marche ?
                </h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                  <div
                    v-for="(step, index) in steps"
                    :key="index"
                    class="text-center"
                  >
                    <div class="w-12 h-12 bg-indigo-600 text-white rounded-full flex items-center justify-center mx-auto mb-4 text-xl font-bold">
                      {{ step.step }}
                    </div>
                    <h3 class="text-xl font-semibold text-gray-900 mb-2">{{ step.title }}</h3>
                    <p class="text-gray-600">{{ step.desc }}</p>
                  </div>
              </div>
           </div>
         </div>
      </AuthLayout>
    </div>
</template>
