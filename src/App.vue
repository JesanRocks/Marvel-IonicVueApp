<template>
  <ion-app>
   <ion-toolbar color="danger">
     <ion-buttons slot="secondary">
       <img src="./assets/reddit-icon.png" width="50px"/>
     </ion-buttons>
     <ion-tittle style="margin: 10px 10px 10px 10px">
      <img src="./assets/marvel-icon.png" width="100px"/>
     </ion-tittle>
   </ion-toolbar>
<!--     <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <ion-content color="light">
     <router-view/> 
    </ion-content>
  </ion-app >
</template>