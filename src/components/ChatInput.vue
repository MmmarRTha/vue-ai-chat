<script setup lang="ts">
import { ref } from 'vue';

// Props and Emits
const emit = defineEmits<{
    (e: 'submit', message: string, model: string): void;
}>();

// State
const prompt = ref('');
const selectedModel = ref('meta-llama/llama-3.3-70b-instruct:free');

// Available models
const models = [
    {
        value: 'meta-llama/llama-3.3-70b-instruct:free',
        label: 'Llama 3 70B'
    },
    {
        value: 'google/gemma-3-1b-it:free',
        label: 'Gemma 3B'
    },
    {
        value: 'google/gemini-flash-1.5-8b-exp',
        label: 'Gemini Flash'
    },
    {
        value: 'mistralai/mistral-nemo:free',
        label: 'Mistral AI'
    }
]

// Methods
const handleSubmit = () => {
    if (prompt.value.trim()) {
        emit('submit', prompt.value, selectedModel.value)
        prompt.value = '';
    }
};

const clearInput = () => {
    prompt.value = '';
};
</script>

<template>
    <form @submit.prevent="handleSubmit" class="flex flex-col space-y-3 mx-4">
        <label for="prompt" class="text-white font-bold text-2xl text-center">
            How can I help you?
        </label>

        <!-- Textarea Container -->
        <div class="relative">
            <textarea v-model="prompt" name="prompt" id="prompt"
                class="border bg-white p-4 rounded-lg w-full text-lg mb-2 resize-none overflow-hidden min-h-[60px] max-h-[200px]"
                placeholder="Ask anything" rows="1"></textarea>

            <!-- Action Buttons -->
            <div class="absolute top-4 right-2 flex items-center gap-2">
                <button type="button" @click="clearInput" aria-label="Clear"
                    class="size-[24px] rounded-md p-1 hover:bg-red-100 hover:text-pink-500 cursor-pointer">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth="1.5"
                        stroke="red">
                        <path strokeLinecap="round" strokeLinejoin="round" d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>

                <button type="submit" aria-label="Send" class="cursor-pointer pr-2 hover:text-green-400">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 25 25" fill="currentColor" class="size-6">
                        <path fill-rule="evenodd"
                            d="M9 4.5a.75.75 0 0 1 .721.544l.813 2.846a3.75 3.75 0 0 0 2.576 2.576l2.846.813a.75.75 0 0 1 0 1.442l-2.846.813a3.75 3.75 0 0 0-2.576 2.576l-.813 2.846a.75.75 0 0 1-1.442 0l-.813-2.846a3.75 3.75 0 0 0-2.576-2.576l-2.846-.813a.75.75 0 0 1 0-1.442l2.846-.813A3.75 3.75 0 0 0 7.466 7.89l.813-2.846A.75.75 0 0 1 9 4.5ZM18 1.5a.75.75 0 0 1 .728.568l.258 1.036c.236.94.97 1.674 1.91 1.91l1.036.258a.75.75 0 0 1 0 1.456l-1.036.258c-.94.236-1.674.97-1.91 1.91l-.258 1.036a.75.75 0 0 1-1.456 0l-.258-1.036a2.625 2.625 0 0 0-1.91-1.91l-1.036-.258a.75.75 0 0 1 0-1.456l1.036-.258a2.625 2.625 0 0 0 1.91-1.91l.258-1.036A.75.75 0 0 1 18 1.5ZM16.5 15a.75.75 0 0 1 .712.513l.394 1.183c.15.447.5.799.948.948l1.183.395a.75.75 0 0 1 0 1.422l-1.183.395c-.447.15-.799.5-.948.948l-.395 1.183a.75.75 0 0 1-1.422 0l-.395-1.183a1.5 1.5 0 0 0-.948-.948l-1.183-.395a.75.75 0 0 1 0-1.422l1.183-.395c.447-.15.799-.5.948-.948l.395-1.183A.75.75 0 0 1 16.5 15Z"
                            clip-rule="evenodd" />
                    </svg>
                </button>
            </div>
        </div>

        <!-- Model Selector -->
        <div class="flex items-center gap-2">
            <label for="model-select" class="text-white sm:text-xs text-base">
                Agent Model:
            </label>
            <select v-model="selectedModel" id="model-select"
                class="text-center appearance-none bg-gray-800/50 text-white p-1 sm:p-2 rounded-lg cursor-pointer border border-gray-700/50 sm:text-xs text-base focus:outline-none focus:ring-2 focus:ring-cyan-500/50 transition-all duration-200 sm:w-24 w-32 shadow-lg shadow-yellow-300/50 font-medium">
                <option v-for="model in models" :key="model.value" :value="model.value" class="bg-gray-800">
                    {{ model.label }}
                </option>
            </select>
        </div>
    </form>
</template>

<style scoped></style>