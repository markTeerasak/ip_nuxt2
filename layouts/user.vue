<template>
    <v-app id="inspire">
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
                        <v-sheet rounded="lg" min-height="268" class="py-3 px-4">
                            <!--  -->
                            <work/>
                        </v-sheet>
                    </v-col>

                    <v-col cols="12" sm="8">
                        <v-sheet min-height="70vh" rounded="lg" class="px-5 py-7">
                            <!--  -->
                            <nuxt />
                        </v-sheet>
                    </v-col>

                    <v-col cols="12" sm="2">
                        <v-sheet rounded="lg" min-height="268" class="py-3 px-4">
                            <!--  -->
                            <Info/>
                        </v-sheet>
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