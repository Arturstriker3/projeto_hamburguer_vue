<template>
    <div id="nav">
        <router-link id="logo-url" to="/">
            <img id="logo" :src="logo" :alt="alt">
        </router-link>
        <router-link to="/">Home</router-link>
        <router-link to="/Pedidos" v-if="esta_logado">Pedidos</router-link>
        <router-link to="/Acesso">Acesso</router-link>
        
    </div>
    
</template>

<script>
import { mapState } from 'vuex'

    export default {
        
        name: "Navbar",
        props: ["logo","alt",],

        computed: {
                ...mapState ({
                    esta_logado: state => state.esta_logado
                })
        },

        methods: {

        },

        components: {
            
        },

        
    }   
    
    
</script>

<style scoped>
    #nav {
        background-color: #222;
        border-bottom: 4px solid #111;
        padding: 15px 50px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }

    #nav #logo-url {
        margin: auto;
        margin-left: 0;

    }

    #logo {
        width: 40px;
        height: 40px;
    }

    #nav a {
        color: #fbca03;
        text-decoration: none;
        margin: 12px;
        transition: .5s;
    }

    #nav a:hover {
        color: #FFF;


    }
</style>