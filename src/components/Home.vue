<template>
  <div class="flex min-h-screen items-center justify-center bg-cover bg-center" :style="{ backgroundImage: `url(${backgroundImage})` }">
    <div class="backdrop-opacity-60 backdrop-blur-sm mx-6 px-4 py-8 rounded-3xl shadow-xl flex flex-col items-center border-2 border-blue-500 w-96">
      <img class="w-3/5" :src="logoDirey" alt="logo-direy">
      <h1 class="text-gray-500 mt-3 font-bold">Sistema de inventario y ventas</h1>
      <div class="relative w-full mt-6 rounded-md">
        <div class="absolute inset-y-0 left-2 flex items-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-500" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-6-3a2 2 0 11-4 0 2 2 0 014 0zm-2 4a5 5 0 00-4.546 2.916A5.986 5.986 0 0010 16a5.986 5.986 0 004.546-2.084A5 5 0 0010 11z" clip-rule="evenodd" />
          </svg>
        </div>
        <input class="w-full py-1 pl-8 bg-transparent border-2 border-gray-500 text-gray-700 font-medium placeholder:text-gray-500 outline-none focus:border-blue-500 rounded-md" type="text" placeholder="Usuario">
      </div>
      <div class="relative w-full mt-6 rounded-md">
        <div class="absolute inset-y-0 left-2 flex items-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-500" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z" clip-rule="evenodd" />
          </svg>
        </div>
        <input class="w-full py-1 pl-8 bg-transparent border-2 border-gray-500 text-gray-700 font-medium placeholder:text-gray-500 outline-none focus:border-blue-500 rounded-md" type="password" placeholder="Contraseña">
      </div>
      <button class="mt-6 py-1 px-4 rounded-md bg-blue-400 hover:bg-blue-500 font-semibold text-white shadow-sm" @click="reload">Acceder</button>
      <div class="mt-12 text-gray-300 font-semibold">Alexis Serrano | Developer &copy;</div>
    </div>
  </div>
</template>

<script setup>
  import backgroundImage from '@/assets/colors.jpg'
  import logoDirey from '@/assets/logo-direy.png'

  (async () => {
   let response = await axios.get('http://localhost:8080/api/products').then((res) => res.data)
   console.log(response[0].name);
 })()

 function reload(){
  location.reload();
 }
</script>