<!-- El ciclo de vida de un componente se refiere a las diferentes etapas por las que pasa un componente 
  Vue desde su creación hasta su destrucción. 
  Estas etapas incluyen la creación, montaje, actualización y destrucción del componente 
  El ciclo de vida te permite realizar acciones específicas en cada etapa,
 como configurar datos, realizar llamadas a API, 
  suscribirte a eventos y limpiar recursos cuando un componente se destruye.
-->
<!-- Los estados en Vue se refieren a las variables de datos que un componente 
  utiliza para mantener su estado interno. 
  Los estados son propiedades que pueden ser reactivas, lo que significa que cuando cambian, 
  Vue automáticamente actualiza la vista para reflejar esos cambios. -->

<template>
  <div class="contador-container">
    <p v-if="mostrarContador" class="contador">{{ contador }}</p>
    <button @click="montarContador" v-if="!mostrarContador">
      Montar Contador
    </button>

    <div v-if="mostrarContador">
      <br />
      <button @click="desmontarContador">Desmontar Contador</button>
      <button @click="incrementarContador">Incrementar</button>
      <button @click="actualizarContador">Actualizar Contador</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contador: 0,
      mostrarContador: false,
      intervalo: null,
    };
  },
  created() {
    console.log("El componente se ha creado.");
  },
  mounted() {
    console.log("El componente se ha montado en el DOM.");
  },
  beforeUnmount() {
    console.log("El componente se va a desmontar.");
    clearInterval(this.intervalo);
  },
  methods: {
    montarContador() {
      console.log("Montando el contador...");
      this.mostrarContador = true;
    },
    desmontarContador() {
      console.log("Desmontando el contador...");
      this.mostrarContador = false;
      clearInterval(this.intervalo);
    },
    incrementarContador() {
      console.log("Incrementando el contador manualmente...");
      this.contador++;
    },
    actualizarContador() {
      console.log("Actualizando el contador a cero...");
      this.contador = 0;
    },
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
  font-family:Verdana, Geneva, Tahoma, sans-serif;
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
  font-family:Verdana, Geneva, Tahoma, sans-serif;
  font-size: 12px;
}
</style>
