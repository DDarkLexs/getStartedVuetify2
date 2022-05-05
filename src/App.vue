<template>
<v-app>
  <v-navigation-drawer
      app
      class="primary"
      dark
    >
      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    
    </v-navigation-drawer>

 <v-app-bar
      color="primary"
      dense
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Page title</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

 
      </v-menu>
    </v-app-bar>

  <!-- Sizes your content based upon application components -->
  <v-main>

    <!-- Provides the application the proper gutter -->
    <v-container fluid>

      <!-- If using vue-router -->
      <router-view></router-view>
    </v-container>
  </v-main>

   <v-footer
    app
    dark
    padless>

    <v-card
      class="flex"
      flat
      tile>

      <v-card-text class="py-0 white--text text-center">
        {{ new Date().getFullYear() }} — <strong>DDarkCoder</strong>
      </v-card-text>
    </v-card>
     </v-footer>
</v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
     items: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard' },
          { title: 'Account', icon: 'mdi-account-box' },
          { title: 'Admin', icon: 'mdi-gavel' },
        ],
    //
  }),
};
</script>
