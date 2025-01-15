<template>

            <!-- Main del Combate --> 
<!-- escenario  -->
<div class="relative w-full h-screen bg-cover bg-center" :style="{ backgroundImage: 'url(' + escenarioSeleccionado + ')' }">
        <!-- <img :src="escenarioSeleccionado" alt="Escenario"> -->
    
                    <!-- Botón de Menú -->
                    <div>
        <button class="bg-[#ff3b58] text-white px-4 py-2 pr-4 rounded font-bold w-[105px] text-center my-5 ml-5"  @click="$router.push('/')"> Menu </button>
    </div>

                    <!-- contenedor del escenarion del combate --> 
        
            <!-- Header del combate -->
<div class="flex justify-center my-5 gap-[130px] items-center"> 
    <!-- barra de vida personaje1 -->
    <div class="w-[400px] bg-gray-200 rounded-full h-6 overflow-hidden shadown-md "> 
        <div class="bg-green-500 h-full ">
            <p class="text-center font-bold text-white">PERSONAJE 1</p>
        </div>
    </div> 

    <div class="">
        <img src="https://cdn-icons-png.flaticon.com/512/9933/9933537.png" alt="vs" class="w-[100px]">
    </div>
    <!-- barra de vida personaje2 -->
    <div class="w-[400px] bg-gray-200 rounded-full h-6 overflow-hidden shadown-md "> 
        <div class="bg-green-500 h-full ">
            <p class="text-center font-bold text-white">PERSONAJE 2</p>
        </div>
    </div> 
</div> 
        <!-- personajes -->
        <div class=" ">
            <img :src="personajeSeleccionado" alt="Personaje Seleccionado"> 
        </div> 
        
</div>
</template> 

<script>
export default{
    name: 'VistaCombate',
    props:[
        'escenarioSeleccionado',
        'personajeSeleccionado'

    ],
    mounted(){
        console.log(this.escenarioSeleccionado)
        console.log(this.personajeSeleccionado)
    }
}
</script> 
