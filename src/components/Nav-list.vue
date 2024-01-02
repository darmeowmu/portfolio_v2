<template>
    <div>
        <v-list-item rounded="lg" @click="$emit('themeToggle')">
            <v-icon :icon="darkTheme ? 'mdi-white-balance-sunny' : 'mdi-moon-waxing-crescent'"></v-icon>
        </v-list-item>
        <v-list-item rounded="lg" variant="text" href="#projects" :active=false>
            <span class="font-weight-medium">Projects</span>
        </v-list-item>
        <v-list-item rounded="lg" variant="text" href="#about">
            <span class="font-weight-medium">About</span>
        </v-list-item>
        <v-list-item rounded="lg" variant="text" @click="dialog = true">
            <div>
                <span class="font-weight-medium">Contact</span>
                <v-dialog transition="dialog-top-transition" v-model="dialog" activator="parent" width="auto">
                    <Modal @close-dialog="dialog = false" />
                </v-dialog>
            </div>
        </v-list-item>
        <v-list-item rounded="lg" variant="text"
            href="https://drive.google.com/file/d/14_hO2mwjevG_RN7lhgXbM5u8l-2OAvNK/view?usp=sharing">
            <span class="font-weight-medium">Resume</span>
            <v-icon icon="mdi-arrow-top-right-bold-box-outline"></v-icon>
        </v-list-item>

    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Modal from '../components/Modal.vue'

defineProps(['darkTheme'])

const dialog = ref(false)

</script>