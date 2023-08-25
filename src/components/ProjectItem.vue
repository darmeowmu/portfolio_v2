<template>
    <v-card class="mt-3 mb-16" flat>
        <div class="d-flex flex-no-wrap justify-space-between" :class="useMobile ? 'flex-column' : ''">
            <div class="d-flex align-center">
                <div>
                    <v-card-title class="text-h4 font-weight-bold">{{ title }}</v-card-title>
                    <v-card-text>
                        <span class="text-body-1">{{ text }}</span>
                        <br />
                        <v-row>
                            <div v-for="stack in stacks" class="mt-2 mx-1">
                                <v-chip class="mt-2">#{{ stack }}</v-chip>
                            </div>
                        </v-row>
                    </v-card-text>
                    <v-card-actions>
                        <v-btn class="ms-2" variant="outlined" size="large" :href="demo" append-icon="mdi-play-outline">
                            Live Demo
                        </v-btn>
                        <v-btn class="ms-2" variant="outlined" size="large" :href="repo"
                            append-icon="mdi-arrow-top-right-bold-box-outline">
                            Code Repo
                        </v-btn>
                    </v-card-actions>
                </div>
            </div>
            <v-avatar class="avatar elevation-6" :class="useMobile ? 'w-100' : 'w-50'" size="260" rounded="lg"
                variant="text">
                <v-carousel cycle hide-delimiter-background color="blue" height="280">
                    <v-carousel-item v-for="(img, index) of imgLink" :key="index" :src="img" cover>
                        <template #placeholder>
                            <div class="d-flex align-center justify-center fill-height">
                                <v-progress-circular color="grey-lighten-4" indeterminate></v-progress-circular>
                            </div>
                        </template>
                    </v-carousel-item>
                </v-carousel>
            </v-avatar>
        </div>
    </v-card>
</template>

<script setup lang="ts">
import { inject } from 'vue';

defineProps({
    title: String,
    text: String,
    demo: String,
    repo: String,
    imgLink: Array<string>,
    stacks: Array
})

const useMobile = inject<boolean>('useMobile')

</script>