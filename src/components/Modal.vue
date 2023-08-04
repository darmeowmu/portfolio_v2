<template>
    <v-card>
        <v-card-title>Get in touch</v-card-title>
        <v-card-text>
            <form ref="form" id="formID" @submit.prevent>
                <v-responsive width="480">
                    <v-text-field label="Name" name="user_name" v-model="emailData.name" variant="outlined"
                        clearable></v-text-field>
                    <v-text-field label="Email" type="email" name="user_email" v-model="emailData.email.emailAdd"
                        :rules="emailData.email.emailRules" variant="outlined" clearable></v-text-field>
                </v-responsive>

                <v-textarea label="Your Message" name="message" v-model="emailData.message">
                </v-textarea>
                <v-card-actions>
                    <v-btn color="error" @click="$emit('closeDialog')">Close</v-btn>
                    <v-spacer></v-spacer>
                    <v-btn type="submit" append-icon="mdi-send" :loading="loading" @click="sendEmail">Send</v-btn>
                </v-card-actions>
            </form>
        </v-card-text>
    </v-card>
</template>
<script setup lang="ts">
import emailjs from '@emailjs/browser';
import { ref, reactive } from 'vue';

const emit = defineEmits(['closeDialog'])

const form = ref(null)

const emailData = reactive({
    name: '',
    email: {
        emailAdd: '',
        emailRules: [
            (value: string) => {
                if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true
                return 'Email must be valid.'
            },
        ]
    },
    message: ''
})

const loading = ref(false)

function sendEmail() {
    loading.value = true
    
    emailjs.sendForm('service_yykp1rt', 'template_lrb75p7', form.value!, 't3HZoxL26Z23sWdTS')
      .then((result) => {
        loading.value = false
        emit('closeDialog')
        console.log('SUCCESS!', result.text);
      }, (error) => {
        console.log('FAILED...', error.text);
      });
}
</script>