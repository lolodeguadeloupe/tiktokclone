<script setup>
import { ref } from 'vue'
import { Link } from '@inertiajs/vue3'
import '@fortawesome/fontawesome-free/css/all.css';

</script>

<template>
    <div class="min-h-screen bg-gray-50">
      <!-- Navigation -->
      <nav class="bg-white shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex justify-between items-center h-16">
            <div class="flex items-center">
              <Home class="h-8 w-8 text-indigo-600" />
              <span class="ml-2 text-xl font-bold text-gray-900">DomServices</span>
              <div class="ml-10 flex items-baseline space-x-4">
                <Link class="text-gray-700 hover:text-indigo-600" href="/">Accueil</Link>
                <Link class="text-gray-700 hover:text-indigo-600" href="/apropos">À propos</Link>
                <Link class="text-gray-700 hover:text-indigo-600" href="/contact">Contact</Link>  
                <Link class="text-gray-700 hover:text-indigo-600" href="/services">Services</Link>
                <Link class="text-gray-700 hover:text-indigo-600" href="/become-provider">Devenir prestataire</Link>
              </div>
            </div>  
            <div class="flex items-center space-x-4" v-if="$page.props.auth.user">
              <Link class="bg-gray-600 text-white px-4 py-2 rounded-lg hover:bg-gray-700"  href="/profile">Profil</Link>
              <Link class="bg-indigo-600 text-white px-4 py-2 rounded-lg hover:bg-indigo-700" href="/logout" method="post" as="button">Déconnexion</Link>
            </div>
            <div class="flex items-center space-x-4" v-else>  
              <Link class="bg-gray-600 text-white px-4 py-2 rounded-lg hover:bg-gray-700" href="/register">Inscription</Link>
              <span class="text-gray-300">|</span>
              <Link
                class="bg-indigo-600 text-white px-4 py-2 rounded-lg hover:bg-indigo-700"
                href="/login"
              >
                Connexion
              </Link>
            </div>
          </div>
        </div>
      </nav>
            <!-- Page Heading -->
        <header class="bg-white shadow" v-if="$slots.header">
            <div class="mx-auto max-w-7xl px-4 py-6 sm:px-6 lg:px-8">
                <slot name="header" />
            </div>
        </header>
        <main class="p-4">
            <slot />
        </main>
    </div>
</template>
