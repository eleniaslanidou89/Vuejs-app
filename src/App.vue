<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app permanent>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Vuetify
          </v-list-item-title>
          <v-list-item-subtitle>
            Best Todo Ever
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item 
        v-for="item in items" 
        :key="item.title"
        :to="item.to" 
        link>
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

      <v-toolbar-title>Vuetify</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <MainSection />
      <BodySection />
    </v-main>
  </v-app>
</template>

<script>
import MainSection from "@/components/MainSection";
import BodySection from "@/components/BodySection";
export default {
  name: "App",
  components: {
    MainSection,
    BodySection,
  },
  data: () => ({
    drawer: null,
    items: [
      { title: "Todo", icon: "mdi-view-dashboard", to:'MainSection' },
      { title: "About", icon: "mdi-image", to:'BodySection' },
    ],
  }),
};
</script>
