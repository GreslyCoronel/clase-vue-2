 <!-- como crear componentes y enlazarlos -->
 <!-- computed propiedades computadas -->
<script setup>
import { ref , computed } from 'vue'
const users = [
  {
    name:'pepito',
    lastname:' perez',
    age: '30'
  },
  {
    name:'lola',
    lastname:' gómez'
  },
]


 const msg = '✌'
 const num = ref(0)

 num.value = 2
 //método
//  const mostrar = () => { 
//   console.log('me estan llamando')
//  }

 //como declarar un metodo computado
 const  computado = computed(function(){
   // return num.value > 0 ? num.value * 2 : 0 (es lo mismo de abajo)
   if(num.value > 0){
    return num.value * 2
   }else {
    return 0
   }
 })
</script>

<template>
 hola mundo {{ msg }} <br>
  valor {{ num }}<br>
  {{ mostrar }}<br> <!-- llamar la función -->
  valor computado {{ computado }}

  <div v-for="(user, index) in users" :key="index"><!-- cuando se utilice el v-for siempre se debe colocar :key="" -->
    Nombre Completo: {{ user.name }}{{ user.lastname }}<br>
    <span v-if="user.age">
      Edad: {{ user.age }}
    </span>
  </div>
</template>

<style scoped>

</style>
