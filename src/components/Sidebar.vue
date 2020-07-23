<template>
    <div class="ma-12 pa-12">
        <template>
            <v-navigation-drawer
                    permanent
                    expand-on-hover
                    app
            >
                <template>
                    <v-card
                            max-width="500"
                            class="mx-auto"
                    >
                        <v-toolbar
                                color="teal"
                                dark
                        >
                            <v-toolbar-title
                            router to="/" link>Colby Barton</v-toolbar-title>
                            <v-spacer></v-spacer>
                        </v-toolbar>

                        <v-list>


                                <v-list-item
                                        v-for="item in items"
                                        :key="item.title"
                                        :prepend-icon="item.icon"
                                        :append-icon="item.items ? undefined : ''"
                                        router :to="item.route" link
                                >
                                    <v-list-item-content>
                                        <v-list-item-title v-text="item.title"></v-list-item-title>
                                    </v-list-item-content>
                                </v-list-item>
                        </v-list>
                    </v-card>
                </template>
            </v-navigation-drawer>
            <v-main>
                <router-view/>
            </v-main>
        </template>
    </div>
</template>

<script>
   // import cpp from './c++'
    export default {
        name: 'App',
        components: {

        },
        data () {
            return{
                items: [
                    {
                        title: 'My Portfolio',
                        icon: 'mdi-folder',
                        route: '/portfolio',
                    },
                    {
                        title: 'About Me',
                        icon: 'mdi-star',
                        route: '/about',
                    },
                    {
                        title: 'Home',
                        icon: 'mdi-home',
                        route: "/",
                    }
                ]
            }
        }
    }
</script>