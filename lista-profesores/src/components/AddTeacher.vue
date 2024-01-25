<!-- 
  Preofesor: Nombre, Apellidos, telefono, DNI, n materas, check documentación
-->
<template>
  <section class="formSection">
    <form class="form" action="#">
      <input type="text" name="nombre" placeholder="Nombre *" @focus="resetMsj" v-model="teacher.name">
      <input type="text" name="telefono" placeholder="Telefono *" @focus="resetMsj" v-model="teacher.telephone">
      <input type="text" name="DNI" placeholder="DNI *" @focus="resetMsj" v-model="teacher.dni">
      <input type="text" name="materia" placeholder="Materia" @focus="resetMsj" v-model="materia">
        <ul v-show="teacher.materias.length !== 0">
          <li v-for="(materia, index) in teacher.materias" :key="index">{{ materia }}</li>
        </ul>
      <button @click.prevent="addMateria" type="submit">Añadir Materia</button>
      <div>
        <label for="docu">¿Ha entregado la documentación?</label>
        <input type="checkbox" name="docu" placeholder="Docu" v-model="teacher.docu">
      </div>
      <button @click.prevent="addTeacher" type="submit">Añadir Ficha</button>
    </form>
    <div><p class="msj">{{ msj }}</p></div>
  </section>

  <section class="listSection">
    <div class="listaProfes">
      <ul class="teacherCard" v-for="teacher in teachers" :key="teacher.dni">
        <li>Nombre: {{ teacher.name }}</li>
        <li>Telefono: {{ teacher.telephone }}</li>
        <li>DNI: {{ teacher.dni }}</li>
        <li>Materias:
          <ul v-for="(materia,index) in teacher.materias" :key="index">
            <li>{{ materia }}</li>
          </ul>
        </li>
        <li>¿Ha entregado la documentación? <span v-if="teacher.docu">Sí</span><span v-else>No</span></li>
      </ul>
    </div>
  </section>
  
</template>
<script setup>
import { ref } from 'vue';

let teacher = ref({
  name: '',
  telephone: '',
  dni: '',
  materias: [],
  docu: false
})

let materia = ref('')
let teachers = ref([])
let msj = ref('')

const addTeacher = () => {
  if (teacher.value.name !== '' && teacher.value.telephone !== '' && teacher.value.dni !== '' && teacher.value.materias.length !== 0) {
    msj.value = ""
    // ⚠️ teachers.value.push( teacher.value ) <- Si se lo pasaramos así, los datos continuarían referenciados y reactivos, por lo que se borrarían o modificarían si continuamos interactuando con el formulario.
    // Para evitarlo creamos un nuevo objeto dentro de la función, que no estará referncado y guardará una copia del objeto inicial
    teachers.value.push({
      name: teacher.value.name,
      telephone: teacher.value.telephone,
      dni: teacher.value.dni,
      materias: teacher.value.materias,
      docu: teacher.value.docu,
    })

    teacher.value.name = ''
    teacher.value.telephone = ''
    teacher.value.dni = ''
    teacher.value.materias = []
    teacher.value.docu = false
  } else {
      msj.value = "Los campos con * son obligatorios"
  }
}

const addMateria = () => {
  if (materia.value !== '') {
    msj.value = ""
    teacher.value.materias.push(materia.value)
    materia.value= ""
  } else {
    msj.value ="El campo 'Mateira' no puede estar vacío"
  }
}

const resetMsj = () => msj.value = ""

</script>
<style scoped>
  section {
    width: 50%;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 1rem;
  }
  input {
    padding: 1rem
  }
  form {
    width: 100%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    justify-items: flex-start;
  }
  button {
    padding: 1rem;
  }

  .teacherCard {
    border: 1px solid mediumaquamarine;
    padding: 1rem;
    margin: 0;
    list-style: none;
    border-radius: 4px;
  }
</style>