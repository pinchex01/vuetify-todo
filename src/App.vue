<template>
  <v-app id="inspire">
      <v-navigation-drawer 
          v-model="drawer"
          app
          >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Verify Todo
          </v-list-item-title>
          <v-list-item-subtitle>
            Best Todo Ever
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to='item.to'
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        drawer: null,
        items: [
          { title: 'Todo', icon: 'mdi-format-list-checks', to : '/' },
          { title: 'About', icon: 'mdi-help-box', to : '/about' },
        ],
        right: null,
      }
    },
  }
</script>