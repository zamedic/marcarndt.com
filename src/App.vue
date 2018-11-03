<template>
    <v-app>
        <v-navigation-drawer v-model="drawer" fixed app>
            <v-toolbar flat class="transparent">
                <v-list class="pa-0">
                    <v-list-tile avatar>
                        <v-list-tile-avatar>
                            <img src="/img/marc.png">
                        </v-list-tile-avatar>

                        <v-list-tile-content>
                            <v-list-tile-title>Marc Arndt</v-list-tile-title>
                        </v-list-tile-content>
                    </v-list-tile>

                </v-list>
            </v-toolbar>
            <v-list class="pt-0" dense>
                <v-divider></v-divider>

                <v-list-tile
                        v-for="item in items"
                        :key="item.title"
                        @click="$router.push(item.target)"
                >
                    <v-list-tile-action>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-tile-action>

                    <v-list-tile-content>
                        <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>

        </v-navigation-drawer>
        <v-toolbar fixed app>
            <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
            <v-toolbar-title>Marc Arndt</v-toolbar-title>
        </v-toolbar>
        <v-content>
            <v-container fluid>
                <router-view></router-view>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      items: [
        { title: "Home", icon: "dashboard", target: "home" },
        { title: "Career", icon: "question_answer", target: "career" }
      ],
      drawer: null
      //
    };
  }
};
</script>
