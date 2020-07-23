<template>
    <v-footer
            dark
            padless
            app
    >
        <v-card
                flat
                tile
                class="indigo lighten-1 white--text text-center"
                width="100%"
        >
            <v-card-text>
                <v-btn
                        v-for="item in items"
                        :key="item.icon"
                        class="mx-4 white--text"
                        item
                        @click="goToSocial(item.link)"

                >
                    <v-icon size="24px">{{ item.icon }}</v-icon>
                </v-btn>
            </v-card-text>

            <v-card-text class="white--text pt-0">

            </v-card-text>

            <v-divider></v-divider>

            <v-card-text class="white--text">
                {{ new Date().getFullYear() }} — <strong>Colby K. Barton</strong>
            </v-card-text>
        </v-card>
    </v-footer>
</template>

<script>
    export default {
        methods:{
            goToSocial: function(link){
                window.open(link, '_blank')
            }
        },
        data: () => ({
            items: [
                {
                    icon: 'mdi-facebook',
                    link: 'https://www.facebook.com/cbar1010/',
                },
                {
                    icon: 'mdi-linkedin',
                    link: 'https://www.linkedin.com/in/colby-barton-926077122/',
                },
                {
                    icon: 'mdi-instagram',
                    link: 'https://www.instagram.com/barton.colby/',
                },

            ],
        }),
    }
</script>