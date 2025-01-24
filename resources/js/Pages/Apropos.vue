<template>
    <AuthLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                À propos
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <div class="about-us">
                            <section class="hero">
                                <div class="hero-content">
                                    <h1>À propos de DomServices</h1>
                                    <p class="subtitle">La plateforme qui révolutionne la mise en relation entre clients et prestataires de services à domicile.</p>
                                </div>
                            </section>

                            <section class="problem-solution">
                                <div class="container">
                                    <h2>Le problème que nous résolvons</h2>
                                    <p>Trouver des services à domicile de qualité à un prix juste relève souvent du défi. Pour les clients, la recherche est longue et fastidieuse, sans garantie de satisfaction. Pour les prestataires, développer et fidéliser une clientèle peut s'avérer complexe et coûteux.</p>
                                    <h2>Notre solution : une plateforme automatisée et efficace</h2>
                                    <p>DomServices connecte directement les clients et les prestataires, éliminant les intermédiaires et simplifiant l'accès aux services. Notre plateforme automatisée vous offre une solution efficace et transparente pour tous vos besoins.</p>
                                </div>
                            </section>

                            <section class="benefits">
                                <div class="container">
                                    <h2>Les avantages pour vous</h2>
                                    <div class="benefits-grid">
                                        <div class="benefit-card">
                                            <h3>Pour les clients :</h3>
                                            <ul>
                                                <li><strong>Coûts réduits :</strong> Accédez à des services de qualité à des prix justes, sans frais cachés.</li>
                                                <li><strong>Transparence totale :</strong> Consultez les profils des prestataires, les avis et les tarifs en toute clarté.</li>
                                                <li><strong>Simplicité et rapidité :</strong> Trouvez et réservez le service idéal en quelques clics.</li>
                                            </ul>
                                        </div>
                                        <div class="benefit-card">
                                            <h3>Pour les prestataires :</h3>
                                            <ul>
                                                <li><strong>Volume d'affaires accru :</strong> Développez votre clientèle grâce à une plateforme dédiée et visible.</li>
                                                <li><strong>Gestion simplifiée :</strong> Gérez vos réservations, votre planning et vos paiements de manière centralisée.</li>
                                                <li><strong>Commission équitable :</strong> Bénéficiez d'un système de commission transparent et avantageux.</li>
                                            </ul>
                                        </div>
                                    </div>
                                </div>
                            </section>

                            <section class="mission">
                                <div class="container">
                                    <h2>Notre mission</h2>
                                    <p>Nous avons pour mission de révolutionner le marché des services à domicile en créant un écosystème plus accessible, efficace et bénéfique pour tous. Rejoignez la communauté DomServices et découvrez une nouvelle façon deSimplified service à domicile !</p>
                                </div>
                            </section>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthLayout>
</template>

<script>
import AuthLayout from '@/Layouts/AuthLayout.vue';

export default {
    name: 'About',
    components: {
        AuthLayout,
    }
}
</script>

<style scoped>
.about-us {
    font-family: 'Arial', sans-serif;
    color: #333;
}

.hero {
    background-color: #f0f7ff;
    padding: 100px 0;
    text-align: center;
}

.hero-content h1 {
    font-size: 2.5rem;
    margin-bottom: 20px;
    color: #1e40af;
}

.hero-content .subtitle {
    font-size: 1.2rem;
    color: #6b7280;
}

.problem-solution, .benefits, .mission {
    padding: 80px 0;
}

.container {
    max-width: 960px;
    margin: 0 auto;
    padding: 0 20px;
}

h2 {
    font-size: 2rem;
    color: #1e40af;
    margin-bottom: 30px;
    text-align: center;
}

.benefits-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;
}

.benefit-card {
    background-color: #fff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
}

.benefit-card h3 {
    font-size: 1.5rem;
    color: #1e40af;
    margin-bottom: 20px;
}

.benefit-card ul {
    list-style: none;
    padding: 0;
}

.benefit-card li {
    margin-bottom: 10px;
    line-height: 1.6;
}

.mission p {
    font-size: 1.2rem;
    line-height: 1.8;
    text-align: center;
}
</style>