<template>
  <div>
  <ion-card>
    <ion-card-header>
      <ion-card-subtitle v-if="image"><img :src="image" alt=""></ion-card-subtitle>
      <ion-card-title>{{publicacion.title}}</ion-card-title>
    </ion-card-header>
    <ion-card-content style="text-align: justify">
      <div  v-if="publicacion.selftext">{{publicacion.selftext}}</div>
      <ion-button expand="block" @click="$router.go(-1)" color="primary">Regresar</ion-button>
    </ion-card-content>
  </ion-card>
  </div>
</template>
<script>
 export default{
  props:['publicacion'],
  data() {
   return{
     image: ''
   };
  },
  mounted(){
   this.image = this.publicacion.preview.images[0].source.url.replace('&amp;','&');
   console.log(this.publicacion);
  }
 };
</script>