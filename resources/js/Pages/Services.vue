<script setup>
import { ref, computed } from 'vue'
import { Link , Head} from '@inertiajs/vue3'
import AuthLayout from '@/Layouts/AuthLayout.vue';
import {
  Home,
  Sparkles,
  Shirt,
  Wrench,
  Flower,
  User,
  Scissors,
  Clock,
  CreditCard,
  Wrench as WrenchIconLucide, // Alias pour éviter la collision de nom
} from 'lucide-vue-next';

const categories = [
  'Tous', 
  'Ménage', 
  'Jardinage', 
  'Bricolage', 
  'Repassage',
  'Garde d\'enfants'
]

const selectedCategory = ref('Tous')

const services = [
  {
    id: 1,
    name: 'Ménage standard',
    description: 'Nettoyage complet de votre intérieur : aspirateur, lavage des sols, dépoussiérage',
    category: 'Ménage',
    price: 25,
    icon: 'Home'
  },
  {
    id: 2,
    name: 'Ménage approfondi',
    description: 'Nettoyage détaillé incluant rangement, nettoyage des vitres et des surfaces',
    category: 'Ménage',
    price: 35,
    icon: 'Sparkles'
  },
  {
    id: 3,
    name: 'Repassage',
    description: 'Repassage soigné de vos vêtements, chemises, pantalons, robes',
    category: 'Repassage',
    price: 20,
    icon: 'Shirt'
  },
  {
    id: 4,
    name: 'Petites réparations',
    description: 'Petits travaux de bricolage : montage de meubles, fixation, petites réparations',
    category: 'Bricolage',
    price: 30,
    icon: 'WrenchIconLucide'
  },
  {
    id: 5,
    name: 'Jardinage',
    description: 'Entretien de votre jardin : tonte, désherbage, taille des haies',
    category: 'Jardinage',
    price: 28,
    icon: 'Flower'
  },
  {
    id: 6,
    name: 'Baby-sitting',
    description: 'Garde d\'enfants, activités éducatives, aide aux devoirs',
    category: 'Garde d\'enfants',
    price: 22,
    icon: 'User'
  },
  {
    id: 8,
    name: 'Couture et retouches',
    description: 'Réparations, ourlets, ajustements de vêtements',
    category: 'Repassage',
    price: 25,
    icon: 'Scissors'
  },
   {
    id: 9,
    name: 'Bricolage avancé',
    description: 'Travaux de bricolage plus complexes',
    category: 'Bricolage',
    price: 40,
    icon: 'Wrench'
  }
]

const filteredServices = computed(() => {
  return selectedCategory.value === 'Tous' 
    ? services 
    : services.filter(service => service.category === selectedCategory.value)
})
</script>

<template>
    <AuthLayout>
      <div class="min-h-screen bg-gray-50">
        <div class="max-w-6xl mx-auto px-4 py-12 sm:px-6 lg:px-8">
          <!-- En-tête de la page -->
          <div class="text-center mb-16">
            <h1 class="text-4xl font-bold text-gray-900 mb-4">
              Nos Services Domestiques
            </h1>
            <p class="text-xl text-gray-600">
              Des services professionnels à portée de clic, facturés à l'heure
            </p>
          </div>
    
          <!-- Filtres de services -->
          <div class="mb-12">
            <div class="flex flex-wrap justify-center gap-4">
              <button 
                v-for="category in categories" 
                :key="category"
                @click="selectedCategory = category"
                :class="[
                  'px-4 py-2 rounded-lg transition-colors duration-300',
                  selectedCategory === category 
                    ? 'bg-indigo-600 text-white' 
                    : 'bg-gray-200 text-gray-700 hover:bg-gray-300'
                ]"
              >
                {{ category }}
              </button>
            </div>
          </div>
    
          <!-- Liste des services -->
          <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div 
              v-for="service in filteredServices" 
              :key="service.id" 
              class="bg-white rounded-2xl shadow-lg p-6 hover:shadow-xl transition-shadow"
            >
              <div class="flex items-center mb-4">
                <LucideVue
                  :name="service.icon"
                  class="h-12 w-12 text-indigo-600 mr-4"
                />
                <h3 class="text-2xl font-semibold text-gray-900">
                  {{ service.name }}
                </h3>
              </div>
              
              <p class="text-gray-600 mb-4">
                {{ service.description }}
              </p>
              
              <div class="flex justify-between items-center">
                <div class="text-lg font-bold text-indigo-600">
                  {{ service.price }}€ / heure
                </div>
                
                <button 
                  class="bg-indigo-600 text-white px-4 py-2 rounded-lg hover:bg-indigo-700 transition-colors"
                >
                  Réserver
                </button>
              </div>
            </div>
          </div>
    
          <!-- Tarification et informations -->
          <div class="mt-16 bg-white rounded-2xl shadow-lg p-8">
            <h2 class="text-3xl font-semibold text-gray-900 mb-6 text-center">
              Notre modèle de tarification
            </h2>
            
            <div class="grid md:grid-cols-3 gap-8">
              <div class="text-center">
                <LucideVue name="Clock" class="h-12 w-12 text-indigo-600 mx-auto mb-4" />
                <h3 class="text-xl font-semibold text-gray-900 mb-2">
                  Facturation à l'heure
                </h3>
                <p class="text-gray-600">
                  Payez uniquement le temps effectué, sans frais cachés
                </p>
              </div>
              
              <div class="text-center">
                <LucideVue name="CreditCard" class="h-12 w-12 text-indigo-600 mx-auto mb-4" />
                <h3 class="text-xl font-semibold text-gray-900 mb-2">
                  Flexibilité
                </h3>
                <p class="text-gray-600">
                  Réservez de 1h à plusieurs heures selon vos besoins
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
  </AuthLayout>
</template>