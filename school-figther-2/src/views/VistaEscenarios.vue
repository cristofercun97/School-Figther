<template>
    <section class="h-screen  bg-center  flex justify-center flex-col items-center landscape:bg-[url('https://cdn.vectorstock.com/i/500p/23/96/ring-octagon-arena-for-boxing-fight-and-mma-vector-45072396.jpg')]">
    <h1 class="text-5xl font-bold text-center text-white p-5 ">SCHOOL FIGTHER</h1>
    <p  class="w-[60%] text-1xl  text-center text-white mb-5 ">SELECCIONA EL ESCENARIO QUE MAS TE GUSTE</p>
    
    
    <!-- Dropdown de escenarios -->
    
    <div class="flex w-full justify-center items-center gap-6 mt-[50px]" >
         
         <select class="bg-white border border-gray-300 text-start rounded-lg focus:ring-blue-50 block w-1/3 scroll-pl-2.5" v-model="escenarioSeleccionado">
            <option disabled value="">Selecciona el Escenario</option>
             <option v-for="(escenario, index) in escenarios " :key="index" :value="index">{{ escenario.nombre }}</option>
         </select>
         {{ personaje1 }}

    </div>
    
    <!-- Debug (opcional) -->
    <div class="mt-4 text-white">
            Escenario seleccionado: {{ escenarios[escenarioSeleccionado]?.imagen }}
        </div>

    <div class=" flex gap-9 mt-[25px] " >
        <div class="flex justify-center my-5">
            <button class="bg-[#3DBC1E] text-white px-4 py-2 rounded font-bold w-[105px] text-center" @click="continuar">Continuar</button>
        </div>

        <div class="flex justify-center my-5">
            <button class="bg-[#ff3b58] text-white px-4 py-2 pr-4 rounded font-bold w-[105px] text-center " @click="$router.push('/')">Volver</button>
        </div> 
    </div>
    
    </section>
</template> 

<script>
import { escenarios } from '../db/db.js';

export default {
    name: 'VistaEscenarios',
    data() {
        return {
            escenarios: escenarios, // Lista de escenarios
            escenarioSeleccionado: '', // Índice del escenario seleccionado
        };
    },
    methods: {
        continuar() {
            // Verificar si se ha seleccionado un escenario
            if (this.escenarioSeleccionado !== '') {
                this.$router.push({
                    name: 'combate',
                    params: {
                        escenarioSeleccionado: this.escenarios[this.escenarioSeleccionado].imagen, // Enviamos el objeto completo
                    },
                });
            } else {
                alert('Selecciona un escenario para poder continuar'); // Alerta si no se selecciona un escenario
            }
        },
    },
};
</script>