<template>
    <v-app id="inspire">
    <v-overlay v-model="overlay" contained class="align-center justify-center">
            <v-row class="my-3">
                <v-btn color="success" @click="overlay = false">
                    <v-icon class="me-1">mdi-logout-variant</v-icon>
                    logout
                </v-btn>
            </v-row>
            <v-row class="my-3">
                <v-btn color="error" @click="overlay = false">
                    <v-icon class="me-1">mdi-logout-variant</v-icon>
                    logout
                </v-btn>
            </v-row>
        </v-overlay>
        <v-app-bar flat>
            <v-avatar :color="$vuetify.breakpoint.smAndDown ? 'grey darken-1' : 'transparent'" size="32"></v-avatar>
            
            <v-tabs centered class="ml-n9" color="grey darken-1">
                <v-tab v-for="(item, link) in links" :key="link" :to="item.to">
                    {{ item.title }}
                </v-tab>
            </v-tabs>
            <v-btn @click="overlay = !overlay" icon mdi-account-circle>
                <v-avatar class="hidden-sm-and-down" color="grey darken-1 shrink" size="32" ></v-avatar>
            </v-btn>
        </v-app-bar>
        <v-main>
            <v-container>
                <v-row>
                    <v-col cols="12" sm="2">
                        <v-card rounded="lg" min-height="268" class="py-3 px-4">
                            <!--  -->
                            <work/>
                        </v-card>
                    </v-col>

                    <v-col cols="12" sm="8">
                        <v-card min-height="70vh" rounded="lg" class="px-5 py-7">
                            <!--  -->
                            <nuxt />
                        </v-card>
                    </v-col>

                    <v-col cols="12" sm="2">
                        <v-card rounded="lg" min-height="268" class="py-3 px-4">
                            <!--  -->
                            <Info/>
                        </v-card>
                    </v-col>
                </v-row>
            </v-container>
        </v-main>
    </v-app>
</template>
  
<script>
import Info from '../components/info.vue'
import work from '../components/work.vue'
export default {
    data: () => ({
        links: [
        {
          title: 'home',
          to: '/',
        },
        {
          title: 'info',
          to: '/info',
        },
        {
          title: 'schedule',
          to: '/schedule',
        },

        ],
        overlay: false,
    }),
    components: {
        Info,
        work
    }
}
</script>
