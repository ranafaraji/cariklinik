<template>
    <v-container>
        <v-row dense>
            <v-col md="3" lg="3" sm="12" v-for="(item, index) in getKliniks" :key="item.id">
                <v-hover
                  v-slot="{ hover }"
                  :key="index"
                >
                <v-card
                  :elevation="hover ? 12 : 2"
                  class="max-auto pa-1"
                  height="250"
                  max-width="300"
                > 
                <v-img v-if="!item.image" :src="url"/>
                <v-img v-else :src="item.image"/>
                <b>{{ item.name }}</b>
           <v-card-actions class="mt-4">
                <v-btn flat
                class="mt-4"
                height="30"
                color="grey lighten-3"
                >Hubungi
                </v-btn>
            
                <v-btn flat
                class="mt-4"
                height="30"
                color="light-blue"
                >Navigasi
                </v-btn>
             </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
     
      <!-- foter v-pagination -->
    <div class="text-center">
    <v-pagination 
    v-on:click="pagination"
      v-model="page"
      :length="24"
      :total-visible="7"
    ></v-pagination>

  </div>
    </v-container>
</template>
<script>
import axios from 'axios'
export default {
    data:() => ({
        page: 0,
        radius:1,
        latitude:3.181017,
        longitude:101.6954547,
        url: "https://api.cariklinik.com/media/def.png",
        getKliniks: []
      
    }),
    created () {
       axios.get('https://api.cariklinik.com/kelinik/?page=2&radius=1&search=&latitude=3.181017&longitude=101.6954547').then(
            response => {
                console.log('response', response);
                this.getKliniks = response.data.results
                console.log('kilinik', this.getKliniks);
            },
       )
  },
  methods: {
      pagination() {
           axios.post('https://api.cariklinik.com/kelinik/', {
           page: this.page,
           radius: this.radius,
           latitude: this.latitude,
           longitude: this.longitude

       }).then(response => {
           this.getKliniks = response.data.results
           console.log('res', response)
       })       
      }
  }
}
</script>

<style scoped>
v-card {
  z-index: 1 !important;
}
</style>