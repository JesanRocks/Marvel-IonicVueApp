<template>
 <div>
  <ion-card v-for="publicacion in publicaciones" :key="publicacion.data.id" style="border:1px solid red">
   <ion-card-content>
    <div v-if="publicacion.data.thumbnail.startsWith('https://')">
     <img :src="publicacion.data.thumbnail" alt="">
    </div>
    <ion-label color="dark">{{publicacion.data.title}}</ion-label><br/>
    <ion-button expand="full" @click="verMas(publicacion.data)">Ver más</ion-button>
   </ion-card-content>
  </ion-card>
 </div>
</template>
<script>
import axios from 'axios';
export default {
    name: "home",
    components: {},
	data() {
		return{
			publicaciones: [],
      image:[]
		};
	},
	async mounted(){
		const respuesta = await axios.get('https://www.reddit.com/r/marvelstudios.json');
		this.publicaciones = respuesta.data.data.children;
		// console.log(this.publicaciones);
		// console.log('Componente montado');
	},
	methods: {
     verMas(publicacion){
      this.$router.push({name: 'detalles', params: {publicacion}})
      // console.log(publicacion.title);
     }
	}
};
</script>
