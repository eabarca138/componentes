<template>
    <div class="componente">
        <div class="boton">
        <button type="button" @click="obtenerData">Obtener personajes</button>
        </div>

        <div class="container personaje" v-for="personaje in personajes" :key="personaje">
            <img :src="personaje.image" alt="personaje">
            <span>{{personaje.name}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Componente",

    data() {
        return {
            personajes: [], 
        }
    },

    methods: {
    async obtenerData() {
            const url = "https://rickandmortyapi.com/api/character"

            try {
                const req = await fetch(url)
                const reqJSON = await req.json()
                this.personajes = reqJSON.results
                console.log(this.personajes);
            } catch (error) {
                console.log(error);
            }
        }
    },
    }
</script>

<style lang="scss" scoped>
img{
            clip-path: circle(50%);
            width: 12.5rem;
            height: 12.5rem;
            margin-right: 1rem;
        }
span{
    font-size: 1.7rem;
    font-weight: bold;
    color: rgb(16, 224, 16);
}

.boton{
    margin: 2rem auto;
    text-align: center;
}

button{
    color: white;
    background-color: rgb(16, 224, 16);
    padding: 1rem;
    border-radius: 15px;
    border-style: none;
    font-size: 1.7rem;
    text-transform: uppercase;
    }

    button:hover{
        background-color: rgb(11, 117, 11);
    }

.personaje{
    margin-top: 1.5rem;
}

.componente{
    font-family: 'Shadows Into Light', cursive;
}
</style>