<template>
    <div>
        <v-card align="center">
            <h1>Colby Barton</h1>
            <h4>I like to rock climb, hike, swim, sail, and have a good time. I graduate from Utah Valley Universtiy Spring 2020 with a BS in Computer Science,
                I currently work at DigiCert, Inc. I love to develop code, learn, and pride myself in my ability to solve problems. I am married and have two dogs.</h4>
        </v-card>
        <v-carousel height="850px">
            <v-carousel-item
                    v-for="(item,i) in items"
                    :key="i"
                    :src="fetchImage(item.src)"
            ></v-carousel-item>
        </v-carousel>
    </div>

</template>

<script>
    export default {
        methods: {
            fetchImage: function(path){
                return require( '../assets/selfie/' + path);
            },
        },
        data () {
            return {
                items: [
                    {
                        src: 'wedding.jpg',
                    },
                    {
                        src: 'fire.jpg',
                    },
                    {
                        src: 'climb.jpg',
                    },
                    {
                        src: 'family.jpg',
                    },
                    {
                        src: 'water.jpg'
                    }
                ],
            }
        },
    }
</script>