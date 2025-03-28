<template>
    <div class="container">
        <h3 class="mt-4 text-center">HORARIO DE CLASES DE SISTEMAS</h3>
        <table class="table table-bordered text-center">
            <thead class="table-dark">
                <tr>
                    <th scope="col">HORA</th>
                    <th scope="col">LUNES</th>
                    <th scope="col">MARTES</th>
                    <th scope="col">MIERCOLES</th>
                    <th scope="col">JUEVES</th>
                    <th scope="col">VIERNES</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(clase, rowIndex) in Horario" :key="rowIndex">
                    <td class="fw-bold">{{ clase.hora }}</td>
                    <td v-for="(dia, colIndex) in ['lunes', 'martes', 'miercoles', 'jueves', 'viernes']"
                        :key="colIndex"
                        :class="getColor(rowIndex, colIndex)">
                        {{ clase[dia] }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const Horario = ref([
    { hora: '07:00-09:00', lunes: 'Programación Lógica y Funcional', martes: 'Inteligencia Artificial', miercoles: 'Desarrollo Ágil', jueves: 'Programación Lógica y Funcional', viernes: '' },
    { hora: '09:00-11:00', lunes: 'Desarrollo Ágil', martes: 'Administración De Redes', miercoles: '', jueves: 'Administración De Redes', viernes: '' },
    { hora: '10:00-11:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Desarrollo Ágil' },
    { hora: '11:00-12:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Desarrollo En La Nube' },
    { hora: '11:00-13:00', lunes: '', martes: 'Desarrollo En La Nube', miercoles: 'Desarrollo En La Nube', jueves: 'Inteligencia Artificial', viernes: '' },
    { hora: '12:00-13:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: '' },
    { hora: '13:00-14:00', lunes: '', martes: '', miercoles: '', jueves: 'Desarrollo Con Realidad Aumentada', viernes: '' },
    { hora: '13:00-15:00', lunes: '', martes: '', miercoles: 'Desarrollo Con Realidad Aumentada', jueves: '', viernes: '' },
    { hora: '14:00-16:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Taller De Investigación II' },
    { hora: '15:00-17:00', lunes: '', martes: 'Desarrollo Con Realidad Aumentada', miercoles: 'Taller De Investigación II', jueves: '', viernes: '' },
])

// Alterna entre rosa y azul en cada celda
const getColor = (row, col) => {
    return (row + col) % 2 === 0 ? 'bg-pink' : 'bg-blue';
}
</script>

<style scoped>
/* Colores personalizados */
.bg-pink {
    background-color: #ffb6c1 !important;
    color: #000;
}
.bg-blue {
    background-color: #add8e6 !important;
    color: #000;
}

/* Bordes y diseño general */
.table th, .table td {
    vertical-align: middle;
    border: 1px solid #ccc;
}
</style>
