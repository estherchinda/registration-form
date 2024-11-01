<template>
    <div class="flex justify-center items-center my-[30px] flex-col">
        <div class="w-[500px]">
            <h1 class="font-bold text-2xl">Lets get started</h1>
            <p class="text-lg my-[15px]">Enter your information just as it appears on your health insurance card or pay stub.</p>
        </div>
        <form class="w-[500px]" @submit="handleSubmission">
            <fieldset class="flex flex-col gap-[15px]">
                <legend class="text-xs my-[10px]">
                    <span class="text-red-700">* </span>Required
                </legend>
                <label for="first-name">
                    First Name <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="last-name">
                    Last Name <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="email">
                    Email <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="country">
                    Country <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="zip-code">
                    ZIP code <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="gender">
                    Sex assigned at birth <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="birth-date">
                    Date of birth <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                <label for="checkbox" class="hover:cursor-pointer">
                    <input type="checkbox" v-model="isChecked">
                    I received a Teladoc Health code from my employer or insurance company.
                </label>
                <div v-if="isChecked">
                    <label for="health-code">
                   Teladoc Health code <span class="text-red-700">*</span>
                    <input 
                    type="text" 
                    class="border border-gray-500 h-[40px] w-full rounded-md px-[15px] text-gray-600 outline-blue-400 mt-4"
                    >
                </label>
                </div>
            </fieldset>
            <button
            @click="handleSubmission"
            type="submit"
            class="bg-blue-500 text-white w-full h-[40px] rounded-md my-[15px] hover:text-blue-500 hover:bg-gray-200 transition-all duration-200">
                Submit
            </button>
        </form>
        <div v-if="isSubmitted" className='fixed inset-0 flex items-center justify-center bg-black bg-opacity-50'>
            <div className='bg-[#D5ED9F] p-6 rounded shadow-lg h-[100px]'>
                <p className='text-gray-700 text-lg'>Form submitted successfully!</p>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    data() {
        return {
            isSubmitted: false
        }
    },
    methods: {
        handleSubmission() {
            this.isSubmitted = true
        }
    },
    setup() {
        const isChecked = ref(false);

        return { isChecked }
    }
}
</script>