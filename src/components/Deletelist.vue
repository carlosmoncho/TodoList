<template>
   <button @click="borrarTodos">Borrar toda la lista</button>
</template>

<script>
export default {
    name: 'delete-list',
    methods: {
        borrarTodos() {
            if (confirm('¿Deseas borrar toda la lista de cosas a hacer?')) {
              this.$emit('delete-all')
            }
          }
      }
}
</script>