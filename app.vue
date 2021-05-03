<template>
    <div>
        <table>
            <tbody>
                <tr v-for="todo in todos" :key="todo.id">
                    <td>{{ todo.id }}</td>
                    
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            todos:null
        }
    },
    mounted(){
        console.log('Hola mundo desde mountend')
        this.getTodos();
    },
    methods: {
        getTodos(){
            console.log('aca va el codigo get todos.')
            axios
            .get('http://127.0.0.1:8000/api/parcial')
            .then( response => {
                console.log(response)
                this.todos = response.data
            } )
            .catch( e=> console.log(e))
        }
    }
}
</script>

<style>

</style>