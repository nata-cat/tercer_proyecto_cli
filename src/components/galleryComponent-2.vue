<template>
    <div id="galleryComponent2">
        <p>{{ mensaje }}</p>
        <button v-on:click="saludar">Saludo</button>

        <h2> {{ title }}</h2>

        <img v-for="imagen in images_src" v-bind:src="imagen" v-bind:key="imagen" alt= "imagen del padre ">
        <h6> {{ pepito }}</h6>
    </div>
</template>

<script>


export default {

    name: 'GalleryComponent2',
    props: {
        title :{
            type: String,
            default: 'El titulo por defecto',
        },
        images_src:{
            type : Array,
            required: true,
        },
        pepito:{
            type: String,
            default: 'Default de pepito',
            required: true,
        },
    },

    data: function(){
        return{
            mensaje: '',
        }
    },
    methods: {
        saludar: function() {
            this.mensaje = 'Oink!'
        }
    },
}

</script>

<style>

#galleryComponent2{
    background-color: rgb(255, 211, 252);
}

button{
    background-color: rgb(204, 50, 155);
    border: none;
    padding: 10px 24px;
    border-radius: 16px;
    color: azure;
}


</style>