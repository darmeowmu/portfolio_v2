<template>
    <v-container fluid class="title-container d-flex align-center ">
        <v-responsive
        >
            <h1 class="font-weight-black" :class="useMobile ? 'text-h4' : 'text-h2'">Hello, I'm Darwin.</h1>
            <h2 class="pt-6" :class="useMobile ? 'text-h6 text-justify' : 'text-h4'">I am a front-end developer who loves building and designing. I'm currently focused on creating
                beautiful web interfaces and applications</h2>
            <div class="d-flex pt-12">
                <v-btn variant="text" icon href="https://github.com/Meowinn"><v-icon icon="mdi-github" size="40px"></v-icon></v-btn>
                <v-btn variant="text" icon href="https://www.linkedin.com/in/darwin-fagarang/" class="mx-8"><v-icon icon="mdi-linkedin" size="40px"></v-icon></v-btn>
                <v-btn variant="text" icon href="https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=darwinfagarang@gmail.com"><v-icon icon="mdi-email" size="40px"></v-icon></v-btn>
            </div>

            <div class="mb-16 pt-16">
                <v-btn class="mr-5 pa-0" variant="text" size="large" href="#projects" :block="useMobile" ><span class="px-2">Look at my work</span>
                    <v-icon icon="mdi-arrow-down"></v-icon></v-btn>
                <v-btn variant="text" size="large" href="https://drive.google.com/file/d/14_hO2mwjevG_RN7lhgXbM5u8l-2OAvNK/view?usp=sharing" :block="useMobile"><span span class="px-2">View Resume</span>
                    <v-icon icon="mdi-arrow-top-right-bold-box-outline"></v-icon>
                </v-btn>

            </div>
            <div class="d-flex justify-center mb-16">
                <a class="scroll-down" href="#projects"></a>
            </div>
        </v-responsive>

    </v-container>
</template>

<script setup lang="ts">
import { inject } from 'vue';

const useMobile = inject<boolean>('useMobile')

</script>
  
<style scoped>

.title-container {
    height: 100vh;
}
.scroll-down {
    height: 50px;
    width: 30px;
    border: 2px solid rgb(56, 56, 56);
    position: absolute;
    left: 50%;
    bottom: 0%;
    border-radius: 50px;
    cursor: pointer;
}

.scroll-down::before,
.scroll-down::after {
    content: "";
    position: absolute;
    top: 20%;
    left: 50%;
    transform: translate(-50%, -100%) rotate(45deg);
    border: 8px solid rgb(42, 43, 43);
    border-radius: 100%;
    border-top: transparent;
    border-left: transparent;
    animation: scroll-down 1.5s ease-in-out infinite;
}

@keyframes scroll-down {
    0% {
        opacity: 0;
    }

    30% {
        opacity: 1;
    }

    60% {
        opacity: 1;
    }

    100% {
        top: 90%;
        opacity: 0;
    }
}
</style>
  
  