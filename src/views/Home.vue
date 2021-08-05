<template>
  <ion-page>
    <ion-header :translucent="true">
      <!-- Logo -->
        <img class="logo" src="https://storage.googleapis.com/game-management-system-181309.appspot.com/ejsc2021/ejsc_logo.png" alt="Swimming logo 2022">
    </ion-header>
    
    <ion-content :fullscreen="true">
      <div id="container">
        <ion-list>
          <ion-list-header>
            <!-- title -->
            <ion-label>
              <h1 class="title">Venue</h1>
            </ion-label>
          </ion-list-header>

          <!-- Section select -->
          <ion-item class="item-interactive item-select item ios in-list ion-activatable ion-focusable hydrated item-label item-has-value">
            <ion-label class="sc-ion-label-ios-h sc-ion-label-ios-s ios hydrated" id="ion-sel-4-lbl" aria-hidden="true">Select Venue</ion-label>
            <!-- Evento onChange -->
            <ion-select v-model="item" value="select" interface="action-sheet" role="button" aria-haspopup="listbox" aria-label="Enable, Notifications" class="ios in-item hydrated select-expanded" @ionChange="venueChange">
            <ion-select-option v-for="venue in venues" :value="venue.code" v-bind:key="venue.id" role="option" id="ion-selopt-2" class="ios hydrated">{{ venue.name }}</ion-select-option>
            <input type="hidden" class="aux-input" name="ion-sel-4" value="enable"></ion-select>
          </ion-item>
        </ion-list>

        <!-- Lists select -->
       <!-- <ion-list class="lists" id="FLEMING">  
          <ion-item>
            <ion-label>lista Grand Hotel Fleming</ion-label>
          </ion-item> 
        </ion-list>
        <ion-list class="lists" id="VMR">
          <ion-item>
            <ion-label>lista Villa Maria Regina</ion-label>
          </ion-item> 
        </ion-list>
        <ion-list class="lists" id="ARANCI">
          <ion-item>
            <ion-label>lista Degli Aranci</ion-label>
          </ion-item> 
        </ion-list>
        <ion-list class="lists" id="VG">
          <ion-item>
            <ion-label>lista Villa Glori</ion-label>
          </ion-item> 
        </ion-list>
        <ion-list class="lists" id="OLY">
          <ion-item>
            <ion-label>lista Olympic Center Giulio Onesti - "Acqua Acetosa"</ion-label>
          </ion-item> 
        </ion-list>
        <ion-list class="lists" id="DL">
          <ion-item>
            <ion-label>lista Donna Laura Palace</ion-label>
          </ion-item>
        </ion-list>
        <ion-list class="lists" id="ORA">
          <ion-item>
            <ion-label>lista Orazio Palace Hotel</ion-label>
          </ion-item>
        </ion-list>
        <ion-list class="lists" id="PAR">
          <ion-item>
            <ion-label>lista Parco dei Principi Hotel & SPA</ion-label>
          </ion-item>
        </ion-list> -->
        
        <!-- Table hotel, transports, time -->
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="hotel"></ion-label>
          </ion-col>
        </ion-row>
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="table-title">GIORNO</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="table-title">ORA PARTENZA</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="table-title">DESTINAZIONE</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="table-title">VEICOLO</ion-label>
          </ion-col>
        </ion-row>
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="content">3/07/2021</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">10:30</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">PISCINA</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">BUS</ion-label>
          </ion-col>
        </ion-row>
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="content">4/07/2021</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">11:30</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">PISCINA</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">BUS</ion-label>
          </ion-col>
        </ion-row>
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="content">6/07/2021</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">12:30</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">PISCINA</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">BUS</ion-label>
          </ion-col>
        </ion-row>
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="content">8/07/2021</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">13:30</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">PISCINA</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">BUS</ion-label>
          </ion-col>
        </ion-row>
        <ion-row class="row">
          <ion-col col-4>
            <ion-label class="content">9/07/2021</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">14:30</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">PISCINA</ion-label>
          </ion-col>
          <ion-col col-4>
            <ion-label class="content">BUS</ion-label>
          </ion-col>
        </ion-row>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonSelect, IonSelectOption } from '@ionic/vue';
import { defineComponent } from 'vue';
import axios from 'axios';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonSelect,
    IonSelectOption
  },
  data () {
    return {
      venues: [],
      item : '',
    }
  },
  created() {
      this.loadVenues();
  },
  methods: {
    loadVenues() {
      axios
        .get('https://ejsc2021.com/event/european-junior-swimming-championships-2021/api/venues/accommodation')
        /* dati API che servono nella select */
        .then(response => (this.venues = response.data.data))
    },
    /* Visualizzo info al click select */
    venueChange(event: any) { 
      console.log(event.detail);
       /* if(event.detail.value !== 'null') {
          Request elements lists 
        const el = Array.from(document.querySelectorAll<HTMLElement>('.lists'));
        el.forEach((element) => {
          element.style.display = 'none';
        });
        document.getElementById(event.detail.value).style.display =  'block';
      } */
       if(event.detail.value !== 'null') {
        /* Request table */
        const el = Array.from(document.querySelectorAll<HTMLElement>('.row'));
        el.forEach((element) => {
          element.style.display = 'block';
        });
        // document.getElementById(event.detail.value).style.display = 'block';
        /* Request hotels */
        const el1 = Array.from(document.querySelectorAll<HTMLElement>('.hotel'));
        el1.forEach((element) => {
          element.innerHTML = event.detail.value;
        });        
      } 
    }
  }
});
</script>

<style scoped>
/* GENERAL */

/* LOGO */
ion-header {
  display: block;
  margin: 0 auto;
  width: 150px;
  height: 122px;
}

ion-header .logo {
  margin-top: 4px;
  height: 110px;
}

#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 20%;
  height: 40%;
  transform: translateY(-50%);
}

#container ion-list > ion-select { 
  /* Set full opacity on the placeholder */
  --placeholder-opacity: 1;
}

/* TITLE */
.title {
  margin-top: 130px;
}

/* SELECTS */
.item-interactive {
  margin-top: 16px;
}

/* LISTS */
.lists {
  display: none;
  margin-top: 20px;
}

/* TABLE */
.row {
  display: none;
  padding: 10px;
  border-bottom: 1px solid #fff;
}

.hotel {
  margin-top: 12px;
}

.table-title {
  padding: 5px;
  font-size: 12px;
}

.content {
  padding: 10px;
}
</style>