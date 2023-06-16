<template>
  <div id="app">
    <h1> El logo es del padre</h1>
    <img id="logo" alt="Vue logo" src="./assets/logo.png">
    
    <GalleryComponent 
    title="mensaje enviado por pato"
    :images_src="images"
    pepito = 'Esta es una foto de pato'
    ></GalleryComponent>

    <p id="parrafoPadre">Esto es parte del componente padre</p>

    <hr>
    

    <GalleryComponent2
    title="Gallery Component 2"
    :images_src="images2"
    pepito = 'Pepito de segundo Componente'>
  </GalleryComponent2>

  <GalleryComponent3 
    title="Componente 3"
    :images_src="images3"
    v-on:delete="eliminarImagen"
    @add="agregarImagen"
    ></GalleryComponent3>

  </div>
</template>

<script>
import GalleryComponent from '@/components/galleryComponent.vue';
import GalleryComponent2 from '@/components/galleryComponent-2.vue';
import GalleryComponent3 from '@/components/galleryComponent3.vue';

export default {
  name: 'App',
  components: {
    GalleryComponent,
    GalleryComponent2,
    GalleryComponent3
  },
  data: function(){
    return{
    images:[
    'https://www.cuartomundo.cl/wp-content/uploads/2015/04/mabel-pines1.png',
    'https://i.pinimg.com/originals/d9/86/8e/d9868eaa577d7df2d1d5eb1866ca306d.png',
    'https://i.pinimg.com/originals/c7/95/a8/c795a8e3947f30b0a96b990fa71db3e0.png',
  ],
  images2:[
    'https://www.nicepng.com/png/full/42-424833_wendy-corduroy-gravity-falls-personajes-de-gravity-falls.png',
    'https://i.pinimg.com/originals/b4/7b/2f/b47b2fad8b23b0b3bf33b61ab23b94c2.png',
    'https://i.pinimg.com/originals/c7/95/a8/c795a8e3947f30b0a96b990fa71db3e0.png',
  ],
  images3:[
    'https://i.pinimg.com/originals/9c/e7/4a/9ce74a8b7ec88ddb95377a26b2c093d2.jpg',
    'https://i.pinimg.com/originals/8b/18/7a/8b187a715d56d5b92f758b3155834409.png',
    'https://www.cuartomundo.cl/wp-content/uploads/2015/04/pacifica-northwest1.png?w=188',
  ],
}},
  methods:{
    eliminarImagen(index){
      this.images3.splice(index, 1);
    },
    agregarImagen(src){
      this.images3.push(src);
    }
  }
}
</script>

<style>

body{
  background-color: rgb(255, 211, 252);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img{
  max-height: 500px;
}

#parrafoPadre{
  background-color: rgb(209, 0, 132);
  color: aliceblue;
  font-size: 12px;
  padding: 16px;
}

#logo{
  width: 300px;
}

</style>

