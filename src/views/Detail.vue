<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Detail</ion-title>
        <ion-buttons slot="start">
          <ion-back-button defaultHref="/"></ion-back-button>
        </ion-buttons>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <h1>Hello from {{ id }}</h1>
      <ion-button @click="toggleStatusBar">Do some native stuff</ion-button>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
  IonBackButton, IonButtons, IonButton
} from '@ionic/vue';
import { useRoute } from 'vue-router';
import {StatusBar} from '@capacitor/status-bar'
const { id } = useRoute().params;
const toggleStatusBar = async () => {
  await StatusBar.hide();
  setTimeout(async () => {
    await StatusBar.show();
  } , 5000)
}
</script>
