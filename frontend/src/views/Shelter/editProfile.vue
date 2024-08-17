<template>
    <form>
        <div class="space-y-12 sm:mx-[1rem] md:mx-[2rem] lg:mx-[5rem]">
            <div class="border-b border-gray-900/10 pb-12">
                <h2 class="text-base font-semibold leading-7 text-gray-900">Shelter Profile</h2>
                <p class="mt-1 text-sm leading-6 text-gray-600">This information will be displayed publicly so be careful what you share.</p>
                <div class="mt-10 border-t pt-[2rem] grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
                    <div class="sm:col-span-3">
                        <label for="petID" class="block text-sm font-medium leading-6 text-gray-900">Shelter's Name</label>
                        <div class="mt-2">
                            <input type="text" name="first-name" id="first-name" autocomplete="given-name" class="block w-full rounded-md border-0 py-1.5 px-[1rem] text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                        </div>
                    </div>
                    <div class="sm:col-span-3">
                        <label for="profile-photo" class="block text-sm font-medium leading-6 text-gray-900">Profile photo</label>
                        <!-- <div class="mt-2 flex justify-center rounded-lg border border-dashed border-gray-900/25 px-6 py-10">
                            <div class="text-center">
                                <PhotoIcon class="mx-auto h-12 w-12 text-gray-300" aria-hidden="true" />
                                <div class="mt-4 flex text-sm leading-6 text-gray-600 justify-center">
                                    <label for="file-upload" class="relative cursor-pointer rounded-md font-semibold text-indigo-600 focus-within:outline-none focus-within:ring-2 focus-within:ring-indigo-600 focus-within:ring-offset-2 hover:text-indigo-500">
                                        <span>Upload a file</span>
                                        <input id="file-upload" name="file-upload" type="file" class="sr-only" />
                                    </label>
                                </div>
                                <p class="text-xs leading-5 text-gray-600">PNG, JPG, GIF up to 10MB</p>
                            </div>
                        </div> -->
                        <!-- <div class="mt-2 flex justify-center rounded-lg border border-dashed border-gray-900/25 px-6 py-10"> -->
                        <div :class="{'py-5': !selectedImage, 'py-2': selectedImage}" class="mt-2 flex justify-center rounded-lg border border-dashed border-gray-900/25">
                            <div class="text-center" v-if="!selectedImage">
                                <PhotoIcon class="mx-auto h-12 w-12 text-gray-300" aria-hidden="true" />
                                <div class="mt-4 flex text-sm leading-6 text-gray-600 justify-center">
                                    <label for="file-upload" class="relative cursor-pointer rounded-md font-semibold text-indigo-600 focus-within:outline-none focus-within:ring-2 focus-within:ring-indigo-600 focus-within:ring-offset-2 hover:text-indigo-500">
                                        <span>Upload a file</span>
                                        <input id="file-upload" ref="fileInput" name="file-upload" type="file" class="sr-only" @change="handleFileChange" />
                                    </label>
                                </div>
                                <p class="text-xs leading-5 text-gray-600">PNG, JPG, GIF up to 10MB</p>
                            </div>
                            <div v-else class="flex justify-center items-center h-full w-full relative">
                                <img :src="selectedImage" class="max-w-[15rem] max-h-[15rem]" />
                                <button @click="clearImage" class="absolute top-2 right-[8.1rem] text-gray-600 hover:text-red-600">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                                    </svg>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="mt-[1rem] grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
                    <div class="col-span-full">
                        <label for="about" class="block text-sm font-medium leading-6 text-gray-900">About Shelter</label>
                        <div class="mt-2">
                            <textarea id="about" name="about" rows="3" class="block w-full rounded-md border-0 py-1.5 px-[1rem] text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                        </div>
                    </div>
                    <div class="col-span-full">
                        <label for="shelter-address" class="block text-sm font-medium leading-6 text-gray-900">Shelter's Location</label>
                        <div class="mt-2 flex gap-x-3">
                            <img :src="Location" alt="Logout Icon" class="w-8 h-8" aria-hidden="true"/>
                            <input type="text" name="shelter-address" id="shelter-address" autocomplete="street-address" class="block w-full rounded-md border-0 py-1.5 px-[1rem] text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                        </div>
                    </div>
                    <div class="sm:col-span-3">
                        <label for="Phone" class="block text-sm font-medium leading-6 text-gray-900">Contact Number</label>
                        <div class="mt-2 flex gap-x-3">
                            <img :src="PhoneNum" alt="Logout Icon" class="w-8 h-8" aria-hidden="true"/>
                            <input type="text" name="Phone" id="Phone" autocomplete="Phone" class="block w-full rounded-md border-0 py-1.5 px-[1rem] text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                        </div>
                    </div>
                    <div class="sm:col-span-3">
                        <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Email address
                        </label>
                        <div class="mt-2 flex gap-x-3">
                            <img :src="Envelope" alt="Logout Icon" class="w-8 h-8" aria-hidden="true"/>
                            <input type="text" name="email" id="email" autocomplete="email" class="block w-full rounded-md border-0 py-1.5 px-[1rem] text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                        </div>
                    </div>
                    <div class="sm:col-span-full">
                        <label for="link" class="block text-sm font-medium leading-6 text-gray-900">Social Link</label>
                        <div class="mt-2 flex gap-x-3">
                            <img :src="Link" alt="Logout Icon" class="w-8 h-8" aria-hidden="true"/>
                            <input id="link" name="link" type="email" autocomplete="link" class="block w-full rounded-md border-0 py-1.5 px-[1rem] text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                        </div>
                    </div>
                </div>
            </div>
            <div class="mt-6 flex items-center justify-end gap-x-6">
                <button type="button" class="text-sm font-semibold leading-6 text-gray-900">Cancel</button>
                <button type="submit" class="rounded-md bgteal px-[2rem] py-2 text-sm font-semibold text-white shadow-sm hover:bg-bgteal focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Save Changes</button>
            </div>
        </div>
    </form>
</template>

<script setup>
import { ref } from 'vue';
import { PhotoIcon } from '@heroicons/vue/24/solid'
import Location from '@/assets/images/Location.png'
import PhoneNum from '@/assets/images/PhoneNum.png'
import Envelope from '@/assets/images/Envelope.png'
import Link from '@/assets/images/link.png'

const fileInput = ref(null);
const selectedImage = ref(null);

function handleFileChange(event) {
  const file = event.target.files[0];
  const reader = new FileReader();
  reader.onload = (event) => {
    selectedImage.value = event.target.result;
  };
  reader.readAsDataURL(file);
}

function clearImage() {
  selectedImage.value = null;
  if (fileInput.value) {
    fileInput.value.value = '';
  }
}
</script>