<script setup lang="ts">
import LogoHeader from './components/LogoHeader.vue';
import Footer from './components/Footer.vue';
import ChatInput from './components/ChatInput.vue';

const handleFormSubmit = (message: string, model: string) => {
  // Handle the form submission
  // This is where you'd typically call your AI service
  console.log('Message:', message)
  console.log('Selected Model:', model)
}
</script>

<template>
    <main class="max-w-3xl mx-auto my-4 px-4 sm:px-6 lg:px-8" role="main">
        <LogoHeader />
        <ChatInput @submit="handleFormSubmit" />
        <Footer />
    </main>
</template>

<style scoped></style>
