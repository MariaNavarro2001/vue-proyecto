<template>
  <div class="min-h-screen flex items-center justify-center bg-gray-100">
    <div class="bg-white p-8 rounded shadow-md w-full max-w-sm">
      <h2 class="text-2xl font-bold mb-6 text-center">Registro</h2>
      <form @submit.prevent="register">
        <div class="mb-4">
          <label class="block text-gray-700">Nombre</label>
          <input
            v-model="name"
            type="text"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            required
          />
        </div>
        <div class="mb-4">
          <label class="block text-gray-700">Carnet</label>
          <input
            v-model="carnet"
            type="text"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            required
          />
        </div>
        <div class="mb-4">
          <label class="block text-gray-700">Correo</label>
          <input
            v-model="email"
            type="email"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            required
          />
        </div>
        <div class="mb-6">
          <label class="block text-gray-700">Contraseña</label>
          <input
            v-model="password"
            type="password"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            required
          />
        </div>
        <div class="mb-6">
          <label class="block text-gray-700">Confirmar Contraseña</label>
          <input
            v-model="confirmPassword"
            type="password"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            required
          />
        </div>
        <button
          type="submit"
          class="w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600"
        >
          Registrarse
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      carnet: '',
      email: '',
      password: '',
      confirmPassword: ''
    }
  },
  methods: {
    register() {
      if (this.email && this.password && this.password === this.confirmPassword) {
        localStorage.setItem('registeredEmail', this.email)
        localStorage.setItem('registeredPassword', this.password)
        this.$router.push('/login')
      } else {
        alert('Las contraseñas no coinciden o faltan campos.')
      }
    }
  }
}
</script>

<style scoped>
/* Puedes agregar estilos adicionales aquí si lo deseas */
</style>
