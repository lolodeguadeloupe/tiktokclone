<template>
    <AuthLayout>
        <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
            <div class="lg:text-center">
                <h2 class="text-base text-indigo-600 font-semibold tracking-wide uppercase">Contactez-nous</h2>
                <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl">
                    Envoyez-nous un message
                </p>
                <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
                    Nous sommes là pour vous aider. N'hésitez pas à nous contacter pour toute question ou demande.
                </p>
            </div>
            <div class="mt-10">
                <div class="md:grid md:grid-cols-1 md:gap-6">
                    <div class="mt-5 md:col-span-2 md:mt-0">
                        <form @submit.prevent="submit">
                            <div class="shadow sm:rounded-md sm:overflow-hidden">
                                <div class="px-4 py-5 bg-white space-y-6 sm:p-6">
                                    <div>
                                        <label for="name" class="block text-sm font-medium text-gray-700">
                                            Nom
                                        </label>
                                        <div class="mt-1">
                                            <input type="text" name="name" id="name" v-model="form.name" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md">
                                            <InputError class="mt-2" :message="form.errors.name" />
                                        </div>
                                    </div>

                                    <div>
                                        <label for="email" class="block text-sm font-medium text-gray-700">
                                            Email
                                        </label>
                                        <div class="mt-1">
                                            <input id="email" name="email" type="email" v-model="form.email" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md">
                                            <InputError class="mt-2" :message="form.errors.email" />
                                        </div>
                                    </div>

                                    <div>
                                        <label for="message" class="block text-sm font-medium text-gray-700">
                                            Message
                                        </label>
                                        <div class="mt-1">
                                            <textarea id="message" name="message" rows="3" v-model="form.message" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md"></textarea>
                                            <InputError class="mt-2" :message="form.errors.message" />
                                        </div>
                                    </div>
                                </div>
                                <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
                                    <button type="submit" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                                        Envoyer
                                    </button>
                                </div>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </AuthLayout>
</template>

<script>
import AuthLayout from '@/Layouts/AuthLayout.vue';
import InputError from '@/Components/InputError.vue';
import { useForm } from '@inertiajs/vue3';

export default {
    components: {
        AuthLayout,
        InputError,
    },
    data() {
        return {
            form: useForm({
                name: '',
                email: '',
                message: '',
            })
        }
    },
    methods: {
        submit() {
            this.form.post('/contact', {
                onSuccess: () => {
                    this.form.reset();
                }
            });
        }
    }
}
</script>