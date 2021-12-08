<template>
    <form @submit.prevent='addNuevo'>
        <input type="text"  v-model="newTarea">
        <button type='submit'>Añadir</button>
    </form>
</template>

<script>
export default {
    name: 'add-todo',
    data(){
        return{
            newTarea: '',
        }
    }, 
    methods:{
        addNuevo(){
              if(this.newTarea){
                  this.$emit('add-Todo', {descrip: this.newTarea, done: false})
                this.newTarea = ' ';
            } 
        }
    }
}

</script>