<template>
    <div id="galleryComponent">
        <p>{{ mensaje }}</p>
        <button v-on:click="saludar">Saludo</button>

        <h2> {{ title }}</h2>

        <img v-for="imagen in images_src" v-bind:src="imagen" v-bind:key="imagen" alt= "imagen del padre ">
        <h6> {{ pepito }}</h6>
    </div>
</template>

<script>



export default {

    name: 'GalleryComponent',
    props: ['title', 'images_src', 'pepito'],

    data: function() {
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

#galleryComponent{
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