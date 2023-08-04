<template>
    <v-card class="mt-3 mb-16" flat>
        <div class="d-flex flex-no-wrap justify-space-between">
            <div class="d-flex align-center">
                <div>
                    <v-card-title class="text-h4 font-weight-bold">{{ title }}</v-card-title>
                    <v-card-text>
                       <span class="text-body-1">{{ text }}</span> 
                        <br />
                        <v-row >
                            <div v-for="stack in stacks" class="mt-2 mx-1" >
                            <v-chip class="mt-2">#{{stack}}</v-chip>
                        </div>
                        </v-row>
                    </v-card-text>
                    <v-card-actions>
                        <v-btn class="ms-2" variant="outlined" size="large" :href="demo" append-icon="mdi-play-outline">
                            Live Demo
                        </v-btn>
                        <v-btn class="ms-2" variant="outlined" size="large" :href="repo" append-icon="mdi-arrow-top-right-bold-box-outline">
                            Code Repo
                        </v-btn>
                    </v-card-actions>
                </div>
            </div>
            <v-avatar class="avatar w-50" size="310"  rounded="lg" variant="outlined">
                <v-img cover class="img" :src="imgLink"></v-img>
            </v-avatar>
        </div>
    </v-card>
</template>

<script setup lang="ts">
defineProps({
    title: String,
    text: String,
    demo: String,
    repo: String,
    imgLink: String,
    stacks: Array
})
</script>