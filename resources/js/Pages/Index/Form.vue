<template>
    <div class="hi">
       <form @submit.prevent="create">
        <div>
          <label>Tarea:</label>
          <input v-model="timer1.tarea" type="text" />
          <h1>{{timer1.tarea}}</h1>        </div>
        <div>
          <button type="submit">Agregar</button>
        </div>
       </form>
    </div>    
    </template>
    <script setup>
      import {reactive } from 'vue'
      import {ref } from 'vue'
      const timer1 = reactive({
        tarea:""
      })
      const x = ref([])

      const createID =()=>{
        const random = Math.random().toString(36).substring(2);
        const fecha = Date.now().toString(36);
        return random+fecha;
      }
      const create =()=>{
        const random = Math.random().toString(36).substring(2);
        const fecha = Date.now().toString(36);
        x.value.push({id: createID() , task1: timer1.tarea, seleccion: false})

      }
    </script>
