<template>
  <v-app>
    <app-nav/>
    <v-main>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-main>
    <v-footer app></v-footer>
  </v-app>
</template>

<script>
import AppNav from '@/components/AppNav.vue';
export default {
  components:{
    AppNav,
  }
  
}
</script>
