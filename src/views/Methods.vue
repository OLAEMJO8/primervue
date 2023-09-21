<!-- Vue.js utiliza un sistema de reactividad más automático y declarativo.
 En Vue.js, defines propiedades de datos (data properties) en tus componentes que actúan como estados. 
 Cuando estos estados cambian, Vue automáticamente detecta los cambios y actualiza la vista para reflejar esos cambios.  -->
 
 <template>
  <div class="contador-container">
    <p class="contador">{{ contador }}</p>
    <button @click="incrementarContador">Incrementar</button>
    <button @click="reiniciarContador">Reiniciar</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    // Utilizamos ref para declarar el contador como una variable reactiva
    const contador = ref(0);

    // Métodos para interactuar con el estado
    const incrementarContador = () => {
      contador.value++;
      console.log('Contador incrementado:', contador.value);
    };

    const reiniciarContador = () => {
      contador.value = 0;
      console.log('Contador reiniciado a 0.');
    };

    return {
      contador,
      incrementarContador,
      reiniciarContador,
    };
  },
};
</script>

<style scoped>
.contador-container {
  text-align: center;
  border: 2px solid #ffffff;
  padding: 20px;
}

.contador {
  text-align: center;
  padding: 10px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 50px;
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

