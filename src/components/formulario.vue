<template>
  <div class="form-container">
    <h2>Formulario de Registro</h2>
    <form @submit.prevent="enviarFormulario">
      <div>
        <label for="nombre">Nombre:</label><br>
        <input type="text" id="nombre" v-model="form.nombre" required>
      </div>

      <div>
        <label for="direccion">Dirección:</label><br>
        <input type="text" id="direccion" v-model="form.direccion" required>
      </div>

      <div>
        <label for="edad">Edad:</label><br>
        <input type="number" id="edad" v-model.number="form.edad" min="0" max="120" required>
      </div>

      <button type="submit">Enviar</button>
    </form>

    <div v-if="mensaje">
      <h3>Datos ingresados:</h3>
      <p>Nombre: {{ form.nombre }}</p>
      <p>Dirección: {{ form.direccion }}</p>
      <p>Edad: {{ form.edad }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        nombre: '',
        direccion: '',
        edad: null
      },
      mensaje: false
    }
  },
  methods: {
    enviarFormulario() {
      // Aquí puedes enviar los datos a un servidor con fetch/axios
      this.mensaje = true;
      console.log('Formulario enviado:', this.form);
      // Opcional: limpiar el formulario
      // this.form = { nombre: '', direccion: '', edad: null };
    }
  }
}
</script>

<style scoped>
.form-container {
  max-width: 400px;
  margin: auto;
  font-family: Arial, sans-serif;
}

label {
  font-weight: bold;
}

input {
  width: 100%;
  padding: 5px;
  margin-bottom: 10px;
  box-sizing: border-box;
}

button {
  padding: 8px 15px;
  cursor: pointer;
}
</style>
