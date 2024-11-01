<template>
    <div class="flex justify-between border-b border-gray-500 mx-[100px]">
        <!-- logo -->
        <div class="flex flex-col items-end px-[10px] pt-[30px] pb-[10px]">
            <h1 class="text-2xl">TELADOC</h1>
            <p class="text-lg text-blue-500 uppercase">Health</p>
        </div>
        <!-- language setting -->
        <div
        @mouseover="handleEnter"
        @mouseout="handleOut" 
        class="flex gap-1.5 items-center w-[80px]">
            <p>icon</p>
            <p class="hover:cursor-pointer font-bold text-lg">ENG</p>
            <ul v-if="isOpen" class="shadow-xl border border-gray-400 rounded-md w-[150px] absolute top-20 bg-gray-100">
                <li v-for="language in languages" :key="language" @click="selectLanguage(language)" class="border-b border-gray-400 hover:bg-blue-500 hover:text-white hover:cursor-pointer p-[5px]">
                    {{ language }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            isOpen: false,
            selectedLanguage: 'Select a language',
            languages: ['English', 'Spanish']
        }
    },
    methods: {
        handleEnter() {
            this.isOpen = true;
        },
        handleOut() {
            this.isOpen = false;
        },
        selectedLanguage(language) {
            this.selectedLanguage = language;
            this.isOpen = false;
        }
    }
}
</script>
