<!--  v-app-bar -->
<template>
  <v-container fluid class="pt-0">
    <v-row class="align center justify-center">
      <v-col sm="12" md="10" lg="10">
        <v-app-bar color="white" elevation="0" hide-on-scroll>
          <div class="d-flex align-center">
            <v-img
              alt="Vuetify Logo"
              class="shrink mr-2"
              contain
              src="https://cariklinik.com/_nuxt/img/icon.1eaeda5.png"
              transition="scale-transition"
              width="40"
            />
            <b class="mt-5">
              <span class="cariColor">cari</span>
              <span>klinik.com</span>
            </b>
          </div>
          <v-spacer></v-spacer>
          <v-btn  small class="light-blue accent-3 white--text">
            <b class="text-lowercase">cari</b>
            <v-icon>
              mdi-magnify-plus-outline
            </v-icon>
          </v-btn>

          <v-btn small class="mx-1" outlined>
            <b class="text-lowercase" color="grey"> Tentang Kami</b>
            <v-icon color="grey darken-2">
              mdi-alert-circle
            </v-icon>
          </v-btn>

          <v-btn small outlined>
            <b class="text-lowercase">Untuk Insitusi</b>
            <v-icon color="grey darken-2 pa-2">mdi-handshake</v-icon>
          </v-btn>
        </v-app-bar>
      </v-col>
    </v-row>
    <v-spacer></v-spacer>
    <!--  v-app-bar -->

    <!-- v-button-navigation -->
    <v-container class="mt-5">
      <v-row justify="center">
        <v-col sm="12" lg="6" md="6">
          <v-bottom-navigation 
           
            color="cyan" 
            height="100" 
          class="elevation-0" background-color="transparent">
            <v-btn value="Klinik">
              <span>Klinik</span>
            
              <v-icon class="sizeIcon  mb-3">mdi-home-plus-outline</v-icon>
              
            </v-btn>

            <v-btn value="Pergigian">
              <span
              
              >Pergigian</span>
              <v-icon class="sizeIcon mb-3">mdi-tooth</v-icon>
            </v-btn>

            <v-btn value="Farmasi">
              <span >Farmasi</span>
              <v-icon class="sizeIcon  mb-3">mdi-pill</v-icon>
            </v-btn>

            <v-btn value="Hospital">
              <span>Hospital</span>
              <v-icon class="sizeIcon  mb-3">mdi-alpha-h-box</v-icon>
            </v-btn>

            <v-btn value="Veterinar">
              <span>Veterinar</span>
              <v-icon class="sizeIcon mb-3">mdi-paw</v-icon>
            </v-btn>
          </v-bottom-navigation>
        </v-col>
      </v-row>
    </v-container>
    <!-- v-button-navigation -->

    <!-- v-toolbar -->
    <v-container>
      <v-row justify="center" align="center">
        <v-col sm="6">
          <v-toolbar dense>
            <v-text-field
             style="box-shadow: none " 
              hide-details="auto"
              prepend-icon="mdi-magnify"
            ></v-text-field>
          </v-toolbar>
        </v-col>
      </v-row>
    </v-container>
    <!-- v-toolbar -->

    <!-- floating -->
  <v-fab-transition>
    <v-row dense>
      <v-btn
        style="flex-direction: row; height: 110px; right: 0; width: 15px; z-index: 2; position: fixed;"
          color="blue"
          direction="top"
          class="btn-toggle"
          dark
          small
          absolute  
          right 
        >
        <span
        style="transform: rotate(-90deg); position: relative; font-size: 15px; top: -9px"
        class="text-lowercase"
         >feedback</span>
        <v-icon style="position: absolute; top: 37px;">mdi-emoticon-neutral-outline</v-icon>
        </v-btn>
       </v-row>
    </v-fab-transition>
 <!-- floating -->

    <v-row>
      <v-col>
        <index />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import index from "../pages/klinic";
export default {
  components: {
    index,
  },
};
</script>

<style scoped>
.cariColor {
  color: #00aeef !important;
  caret-color: #00aeef !important;
}
.sizeIcon {
  font-size: 60px !important;
}
.v-sheet.v-toolbar:not(.v-sheet--outlined) {
    box-shadow: none;
}
.btn-toggle {
  flex-direction: column;
}
</style>
