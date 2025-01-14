<template>
   <section class="h-screen  bg-center  flex justify-center flex-col items-center landscape:bg-[url('https://cdn.vectorstock.com/i/500p/23/96/ring-octagon-arena-for-boxing-fight-and-mma-vector-45072396.jpg')]">
    <h1 class="text-5xl font-bold text-center text-white p-5 ">SCHOOL FIGTHER</h1>
    <p  class="w-[60%] text-1xl  text-center text-white mb-5 ">EL MEJOR JUEGO DE PELEAS ENTRE ALUMNOS, SELECCIONA 
        LOS ALUMNOS QUE VAN A DARSE HOSTIAS</p>
    <div class="flex w-full justify-center items-center gap-6" >
        
        <select class="bg-white border border-gray-300 text-start rounded-lg focus:ring-blue-50 block w-1/3 scroll-pl-2.5" v-model="personaje1">
            <option v-for="(personaje, index) in personajes " :key="index" :value="index">{{ personaje.nombre }}</option>
        </select>
        {{ personaje1 }}


        <select class="bg-white border border-gray-300 text-start rounded-lg focus:ring-blue-50 block w-1/3 scroll-pl-2.5" v-model="personaje2" >
            <option v-for="(personaje, index) in personajes" :key="index" :value="index">{{ personaje.nombre }}</option>
        </select>
        {{ personaje2 }}
    </div>
    <div class="flex justify-center my-5">
        <button class="bg-[#3DBC1E] text-white px-4 py-2 rounded font-bold" @click="$router.push('/escenarios')">Continuar</button>
    </div>
   </section>
</template> 

<script>
import {personajes} from '../db/db.js'
export default{
    name: 'VistaPersonajes',
    data(){
        return{
            personajes: personajes,
            personaje1: '',
            personaje2: ''
        }
    }
}
</script>