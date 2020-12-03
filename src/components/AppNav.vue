<template>
  <v-card>
    <v-app-bar absolute app flat color="#E8F5E9">
      <v-app-bar-nav-icon color="#4CAF50" @click.stop="drawer = !drawer"/>
      <v-toolbar-title>
        <span class="text-h4 font-weight-medium" style="color:#4CAF50">
          <v-icon x-large color="#1B5E20">mdi-tree</v-icon>
          Vegan From Earth
        </span>
      </v-toolbar-title>
      <v-spacer/>
      <v-text-field
        hide-details
        clearable
        single-line
      ></v-text-field>
      <v-btn icon dark><v-icon color="#4CAF50">mdi-magnify</v-icon></v-btn>
      <v-menu left bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon v-bind="attrs" v-on="on">
            <v-icon color="#4CAF50">mdi-dots-vertical</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item><v-list-item-title>HOME</v-list-item-title></v-list-item>
          <v-list-item><v-list-item-title>LOGOUT</v-list-item-title></v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" fixed temporary app>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
            <v-list-item link
                v-for="item in items" :to="item.route"
                :key="item.title"
            >
                <v-list-item-icon>
                    <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-icon>
                <v-list-item-content>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      drawer: false,
      group: null,
      items: [
            { title: 'HOME', icon: 'mdi-home-city', route: '/'},
      ],
    }),

    watch: {
      group () {
        this.drawer = false
      },
    },
  }
</script>

