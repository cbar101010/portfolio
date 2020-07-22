<template>
    <div class="ma-12 pa-12">
        <template>
                <v-navigation-drawer
                        permanent
                        aria-expanded="true"
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
                                <v-app-bar-nav-icon></v-app-bar-nav-icon>

                                <v-toolbar-title>Colby Barton</v-toolbar-title>

                                <v-spacer></v-spacer>
                            </v-toolbar>

                            <v-list>
                                <v-list-group
                                        v-for="item in items"
                                        :key="item.title"
                                        router :to="item.route" link
                                        :prepend-icon="item.icon"
                                        :append-icon="item.items ? undefined : ''"
                                >
                                    <template v-slot:activator>
                                        <v-list-item-content>
                                            <v-list-item-title v-text="item.title"></v-list-item-title>
                                        </v-list-item-content>
                                    </template>

                                    <v-list-item
                                            v-for="subItem in item.items"
                                            :key="subItem.title"
                                            router :to="subItem.route" link
                                    >
                                        <v-list-item-content>
                                            <v-list-item-title v-text="subItem.title"></v-list-item-title>
                                        </v-list-item-content>
                                    </v-list-item>
                                </v-list-group>
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
                        route: '',
                        items: [
                            {title: 'Java', route: '/portfolio'},
                            {title: 'cpp', route: '/portfolio'},
                        ]
                    },
                    {
                        title: 'About Me',
                        icon: 'mdi-star',
                        route: '/about',
                    }
                ]
            }
        }
    }
</script>