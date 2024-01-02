<template>
    <div>
        <h2 class="font-weight-bold">About me</h2>
        <v-divider />
        <v-card flat>
            <div class="d-flex flex-no-wrap justify-space-between" :class="useMobile ? 'flex-column' : ''">
                <div>
                    <v-card-text>
                        <p class="text-justify text-h6">
                            Hi! Thank you for your time and Interest! It's my <strong>goal</strong> to be a
                            <strong>front-end expert.</strong>
                            I have a <strong> passion for designing, learning, and building</strong> things for the web. I
                            like to solve design problems, create interactive interfaces
                            and <strong>develop web features and sites</strong>.
                            <br />
                        </p>
                        <p class="my-5 text-h6">Here are the technologies I've been working with:</p>
                            <v-row class="row align-center">
                                <v-col lg="4" md="4" sm="6" v-for="skill in skills" :key="skill.text">
                                    <li><v-icon :icon="skill.icon"></v-icon> {{ skill.text }}</li>
                                </v-col>
                            </v-row>
                    </v-card-text>
                </div>
                <v-avatar class="align-self-center ma-5" size="200" rounded="pill">
                    <v-img :src="primary"></v-img>
                </v-avatar>
            </div>
        </v-card>
        <v-divider />
        <v-sheet class="my-15 text-center">
            <h1 class="font-weight-black text-h3 py-5">Say hi to Darwin</h1>
            <p class="mb-12 text-body-1">
                I would love to hear from you. Whether it's a project, a job opportunity,
                or just a chat. Feel free to contact me.
            </p>
            <div class="down-arrow"></div>
            <v-btn class="my-16" variant="text" size="large" append-icon="mdi-airplane-takeoff"
                @click="modal = true"><span>Email
                    <v-dialog transition="dialog-bottom-transition" v-model="modal" activator="parent" width="auto">
                        <Modal @close-dialog="modal=false" />
                    </v-dialog>
                </span>
            </v-btn>
        </v-sheet>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Modal from './Modal.vue'
import primary from '../assets/primary.png'
import { inject } from 'vue';

const useMobile = inject<boolean>('useMobile')

const skills = {
    html: {
        icon: 'mdi-language-html5',
        text: 'HTML'
    },
    css: {
        icon: 'mdi-language-css3',
        text: 'CSS3'
    },
    bootstrap: {
        icon: 'mdi-bootstrap',
        text: 'Bootstrap'
    },
    javascript: {
        icon: 'mdi-language-javascript',
        text: 'Javascript'
    },
    typescript: {
        icon: 'mdi-language-typescript',
        text: 'Typescript'
    },
    react: {
        icon: 'mdi-react',
        text: 'React'
    },
    vue: {
        icon: 'mdi-vuejs',
        text: 'Vue3'
    },
    nuxt: {
        icon: 'mdi-nuxt',
        text: 'Nuxt 3'
    },
    graphql: {
        icon: 'mdi-graphql',
        text: 'GraphQL'
    },
    php: {
        icon: 'mdi-language-php',
        text: 'PHP8'
    },
    sql: {
        icon: 'mdi-database-search',
        text: 'SQL'
    },
    git: {
        icon: 'mdi-git',
        text: 'Git/GitHub'
    },
    cms: {
        icon: 'mdi-cog',
        text: 'Content Management Systems'
    }
}

const modal = ref(false)
</script>

<style scoped>
.row {
    font-size: 1.1rem;
}
.down-arrow {
    position: absolute;
    left: calc(50% - 14px);
    width: 0;
    height: 30px;
    border: 2px solid;
    border-radius: 2px;
    animation: jumpInfinite 1.5s infinite;
}

.down-arrow:after {
    content: "";
    position: absolute;
    top: 12px;
    left: -8px;
    width: 16px;
    height: 16px;
    border-bottom: 4px solid;
    border-right: 4px solid;
    border-radius: 4px;
    transform: rotateZ(45deg);
}

@keyframes jumpInfinite {
    0% {
        margin-top: 0;
    }

    50% {
        margin-top: 35px;
    }

    100% {
        margin-top: 0;
    }
}</style>