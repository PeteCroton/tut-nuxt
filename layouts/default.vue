<template>
    <v-app id="inspire">
        <v-system-bar>
            <v-spacer></v-spacer>

            <v-icon>mdi-square</v-icon>

            <v-icon>mdi-circle</v-icon>

            <v-icon>mdi-triangle</v-icon>
        </v-system-bar>

        <v-app-bar>
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

            <v-app-bar-title>Application</v-app-bar-title>
        </v-app-bar>

        <v-navigation-drawer v-model="drawer" temporary>
              <v-card 
                    class="mx-auto bg-grey-lighten-2"
                    max-width="300"
                >
                <v-list :items="items"></v-list>
                </v-card>
        </v-navigation-drawer>

        <v-main class="bg-grey-lighten-2">
            <v-container>
                <slot></slot>
                <!--  -->
            </v-container>
        </v-main>
    </v-app>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(null)
</script>

<script>
export default {
    data: () => ({ drawer: null,
        items: [
            { title: 'Home', icon: 'mdi-home-city' },
            { title: 'My Account', icon: 'mdi-account' },
            { title: 'Users', icon: 'mdi-account-group-outline' },
            { title: 'Logout', icon: 'mdi-logout' },
        ]}),
}
</script>