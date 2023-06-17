<template>
    <div id="galleryComponent3">
        <p>{{ mensaje }}</p>
        <button v-on:click="saludar">Saludo</button>

        <h2> {{ title }}</h2>

        
        <div id="contenedorFotos" v-for="(imagen, index) in images_src" v-bind:key="imagen">
            <img v-bind:src="imagen" alt= "imagen del padre "> <br>
            <button v-on:click.prevent="eliminar(index)">Eliminar</button>
        </div>
        
        <hr>

        <form action="">
            <label for="nuevaImagen">Agrega un link de imagen</label> <br>
            <input type="text" id="nuevaImagen" v-model="newImage"> <br>
            <button v-on:click.prevent="agregar">Agregar</button>
        </form>

    </div>
</template>

<script>



export default {

    name: 'GalleryComponent3',
    props: ['title', 'images_src'],

    data: function() {
        return{
            mensaje: '',
            newImage: '',
        }
    },
    methods: {
        saludar: function() {
            this.mensaje = 'Oink!'
        },
        agregar: function(){
            //Cuando el hijo emita el evento llamado add, el padre lo escucha
            this.$emit('add', this.newImage);
            this.newImage = "";
        },
        eliminar: function(index) {
            this.$emit('delete', index)
        },
    },
}

</script>

<style>

#galleryComponent3{
    background-color: rgb(255, 211, 252);
}

button{
    background-color: rgb(204, 50, 155);
    border: none;
    padding: 10px 24px;
    border-radius: 32px;
    color: azure;
    margin: 8px;
}

input{
    border-radius: 32px;
    height: 32px;
    width: 600px;
    border: solid 1px rgb(246, 200, 246);
    margin-top: 8px;
    padding: 0px 16px;
}

label{
    font-size: 16px;
    font-weight: 600;
    color: deeppink;
}

hr{
    border: dotted rgb(255, 255, 255);
    border-radius: 50%;
}

#contenedorFotos{
    display: inline-block;
    align-items: center;
    justify-content: center;
}


</style>