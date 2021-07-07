<template>
        <div>
            {{tarea.id}} - {{tarea.nombre}}
            <h1>Editar</h1>

            <form action="">
                <input type="text" >
                <button type="submit">Editar</button>
            </form>
        </div>
</template>

<script>
import {mapActions,mapState} from 'vuex'
export default {
        name:'Editar', 
        data() {
            return {
                id: this.$route.params.id
            }
        },
        created(){
                this.getTarea(this.id);
        },
        methods:{
            ...mapActions(['getTarea'])
        },
        computed:{
            ...mapState(['tarea'])
        }
}
</script>
