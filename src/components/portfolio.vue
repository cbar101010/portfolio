<template>
    <div>
        <v-container fluid>

            <v-row>
                <v-col cols="12">
                    <v-row>
<!--                        <template>-->
<!--                            <v-container fluid>-->
<!--                                <v-row class="light&#45;&#45;text">-->
<!--                                    <v-col cols="4">CPP</v-col>-->
<!--                                    <v-col cols="4">Java</v-col>-->
<!--                                    <v-col cols="4">Other</v-col>-->
<!--                                </v-row>-->
<!--                                <v-row>-->
<!--                                    <v-col cols="4">-->
<!--                                        <v-checkbox :input-value="cpp" value></v-checkbox>-->
<!--                                    </v-col>-->
<!--                                    <v-col cols="4">-->
<!--                                        <v-checkbox :input-value="java" value></v-checkbox>-->
<!--                                    </v-col>-->
<!--                                    <v-col cols="4">-->
<!--                                        <v-checkbox  :input-value="web" value ></v-checkbox>-->
<!--                                    </v-col>-->
<!--                                </v-row>-->
<!--                            </v-container>-->
<!--                        </template>-->
                        <template v-for="item in items">
                            <v-card
                                    class="pa-md-4 mx-lg-auto"
                                    max-width="400"
                                    :key="item.title"
                                    v-if="isActive(item.languages)"
                            >
                                <v-img
                                        class="white--text align-end"
                                        height="200px"
                                        :src="fetchImage(item.path)"
                                >
                                </v-img>
                                <v-card-title v-text="item.title"></v-card-title>
                                <v-card-subtitle class="pb-0" v-text="item.subtitle"></v-card-subtitle>
                                <v-card-text class="text--primary">
                                    <div v-text="item.description"></div>
                                </v-card-text>

                                <v-card-actions>
                                    <v-btn
                                            color="orange"
                                            text
                                            @click="goToGitHub(item.github)"
                                    >
                                        View on github
                                    </v-btn>

                                </v-card-actions>
                            </v-card>
                        </template>

                    </v-row>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>
<script>
    export default {
        name: 'projects',
        methods: {
            goToGitHub: function(link) {
                window.open(link, '_blank')
            },
            fetchImage: function(path){
                return require( '../assets/images/' + path);
            },
            isActive: function(language){
                if(language === "cpp" && this.cpp === true){
                    return true
                }
                else if(language === "java" && this.java === true){
                    return true
                }
                else if(language ==="web" && this.java === true){
                    return true
                }
            }
        },
        data () {

            return{
                languages:['C++', 'Java', 'Web'],
                value: ['C++', 'Java', 'Web'],
                cpp: true,
                java: true,
                web: true,
                items: [
                    {
                        title: 'Compiler',
                        description: 'Compiler that was written for language KXI2020, it includes a Lexical Analyzer, Syntax checker, Semantics checker, Intermediate code generation and target code generation. This compiler/kxi supports Class\'s/Object\'s, arrays, functions, recursive functions, loops and other typical language features. Can be used with my Assembler/VM to take source code all the way to machine code',
                        path: 'comp.png',
                        github: 'https://github.com/cbar101010/Compiler',
                        subtitle: 'Technologies: C++',
                        languages: 'cpp',
                        something: true

                    },
                    {
                        title: 'Assembler/VM',
                        subtitle: 'Technologies: C++, assemblers/ISA',
                        description: 'Assembler/VM to run the .asm files from my compiler.',
                        path: 'assembler.jpg',
                        github: 'https://github.com/cbar101010/VM',
                        languages: 'cpp',
                        something: true
                    },
                    {
                        title: 'ChoreMaster',
                        subtitle: 'Technologies: Vue, Vuetify, FireBase (database/authentication), Javascript',
                        description: 'Unfinished Vue project, The idea is an easy way for parents to track their childrens chores, let kids see their rewards. Shows skills in above listed technologies.',
                        path: 'chore.jpg',
                        github: 'https://github.com/cbar101010/choremasters',
                        languages: 'web',
                        something: true
                    },
                    {
                        title: 'AI Genetic Algorithm',
                        subtitle: 'Technologies: C++, AI',
                        description: 'This is a AI genetic algorithm program I wrote to find the maximum and minimum of this function \tf (w,x,y,z)  = (sin(Ω(x+w))2(sin(Ω(y+z))2e-(w+x+y+z)/150. Although this program was built to maxize and minimize the function\n' +
                            'given, it was written in a way it could easily be changed to maximize/minamize any function through machine learning. ',
                        path: 'genetic.png',
                        github: 'https://github.com/cbar101010/AI-GeneticAlgorithms',
                        languages: 'cpp',

                        something: true

                    },
                    {
                        title: 'Photo Album Viewer',
                        subtitle: 'Technologies: Java',
                        description: 'Image viewer written in Java. Allows you to open photo albums, switch between photos, add captions, view in thumbnail mode, and save the album (captions).',
                        path: 'camera.jpeg',
                        github: 'https://github.com/cbar101010/Image-Viewer',
                        languages: 'java',

                        something: true

                    },
                    {
                        title: 'This site!',
                        subtitle: 'Technologies: Vue, Vuetify, Javascript',
                        description: 'My portfolio website (unfinished project)',
                        path: 'portfolio.jpeg',
                        github: 'https://github.com/cbar101010/portfolio',
                        languages: 'web',

                        something: true

                    }
                ]
            }
        }
    }
</script>
