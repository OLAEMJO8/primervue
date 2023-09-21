<!-- <template >
  <div class="contador-container" >
    <p v-if="mostrarContador" class="contador">Contador: {{ contador }}</p>
    <button @click="montarContador" v-if="!mostrarContador">Montar Contador</button>
 
    <div v-if="mostrarContador">
      <br/>
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
      intervalo: null
    };
  },
  created() {
    console.log('El componente se ha creado.');
  },
  mounted() {
    console.log('El componente se ha montado en el DOM.');
  },
  beforeUnmount() {
    console.log('El componente se va a desmontar.');
    clearInterval(this.intervalo);
  },
  methods: {
    montarContador() {
      console.log('Montando el contador...');
      this.mostrarContador = true;
      
    },
    desmontarContador() {
      console.log('Desmontando el contador...');
      this.mostrarContador = false;
      clearInterval(this.intervalo);
    },
    incrementarContador() {
      console.log('Incrementando el contador manualmente...');
      this.contador++;
    },
    actualizarContador() {
      console.log('Actualizando el contador a cero...');
      this.contador = 0; // Vuelve a establecer el contador a cero
    }
  }
};
</script>

  
  <style scoped>
  .contador-container {
  
   
    text-align: center; /* Centra el contenido horizontalmente */
    border: 2px solid #ffffff; /* Agrega un borde al contenedor */
    padding: 20px; /* Añade espacio alrededor del contenido */
  }
  
  .contador {
    text-align: center;
    border: 1px solid #ccc; /* Agrega un borde al contador */
    padding: 10px; /* Espaciado interno para el contador */
    display: inline-block; /* Para que el contador tenga un ancho mínimo */
    
  }
  
  /* Estilos para los botones dentro del contenedor */
  .contador-container button {
   
    padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  }
  </style> -->