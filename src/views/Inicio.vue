<template>
    <div>
        <h1>Inicio</h1>
        <ul>
             <li v-for="item in tareas" :key="item.id">
                {{ item.nombre }} - {{ item.id }}
                <router-link :to="{name:'Editar', params:{ id: item.id}}">
                    <button >Editar</button>
                </router-link>
            </li>

           
        </ul>
    </div>
</template>
<script>
import {mapActions, mapState} from 'vuex'
export default {
    name:'Inicio',
    created(){
     this.getTareas();
    },
    methods:{
        ...mapActions(['getTareas'])
    },
    computed: {
       ...mapState(['tareas'])
    },
}
</script>