<template>
  <div class="contador-container">
    <!-- Mostrar el contador si la variable mostrarContador es verdadera -->
    <p v-if="mostrarContador" class="contador">{{ contador }}</p>
    <!-- Botón para montar el contador si mostrarContador es falso -->
    <button @click="montarContador" v-if="!mostrarContador">
      Montar Contador
    </button>

    <!-- Botones para acciones cuando mostrarContador es verdadera -->
    <div v-if="mostrarContador">
      <br />
      <button @click="desmontarContador">Desmontar Contador</button>
      <button @click="incrementarContador">Incrementar</button>
      <button @click="actualizarContador">Actualizar Contador</button>
    </div>
  </div>
</template>

<script>
import { ref, watchEffect, onBeforeUnmount } from 'vue';

export default {
  setup() {
    // Utilizar ref para declarar variables reactivas
    const contador = ref(0);
    const mostrarContador = ref(false);
    let intervalo;

    // Ciclo de vida: created
    console.log("El componente se ha creado.");

    // Utilizar watchEffect para el ciclo de vida: mounted
    watchEffect(() => {
      if (mostrarContador.value) {
        console.log("El componente se ha montado en el DOM.");
      }
    });

    // Utilizar onBeforeUnmount para el ciclo de vida: beforeUnmount
    onBeforeUnmount(() => {
      console.log("El componente se va a desmontar.");
      clearInterval(intervalo);
    });

    // Métodos para interactuar con el estado
    const montarContador = () => {
      console.log("Montando el contador...");
      mostrarContador.value = true;
    };

    const desmontarContador = () => {
      console.log("Desmontando el contador...");
      mostrarContador.value = false;
      clearInterval(intervalo);
    };

    const incrementarContador = () => {
      console.log("Incrementando el contador manualmente...");
      contador.value++;
    };

    const actualizarContador = () => {
      console.log("Actualizando el contador a cero...");
      contador.value = 0;
    };

    return {
      contador,
      mostrarContador,
      montarContador,
      desmontarContador,
      incrementarContador,
      actualizarContador,
    };
  },
};
</script>

<style scoped>
.contador-container {
  padding: 20px;
  text-align: center;
}

.contador {
  text-align: center;
  padding: 10px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 2rem;
}

.contador-container button {
  padding: 10px 20px;
  background-color: #45236b;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 12px;
}
</style>
