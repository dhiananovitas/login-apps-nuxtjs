<template>
  <v-row id="navbar">
    <v-system-bar height="80" app>
      <v-spacer />
      <router-link to="/" style="display:flex;text-decoration:none;align-items:center;">
        <v-icon>mdi-logout</v-icon>
        <v-list-item-title>Logout</v-list-item-title>
      </router-link>

      
    </v-system-bar>

    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-sheet
        color="grey lighten-4"
        class="pa-4"
      >
        <v-avatar
          class="mb-4"
          color="grey darken-1"
          size="64"
          style="background-color: antiquewhite;margin-left: 35%;margin-bottom: 25px;margin-top: 25px;"
        />

        <div style="text-align:center">User</div>
      </v-sheet>

      <v-divider />

      <v-list>
        <v-list-item
          v-for="[icon, text] in links"
          :key="icon"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container
        class="py-8 px-6"
        fluid
      >
      <Dashboard></Dashboard>
        <nuxt />
      </v-container>
    </v-main>
  </v-row>
</template>

<script>
import Dashboard from "~/components/Dashboard.vue";
export default {
    name: "navbar",
    components: { Dashboard },
    data: () => ({
        drawer: null,
        links: [
        ['mdi-home', 'Dashboard']
        ]
    })
}
</script>