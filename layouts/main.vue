<template>
    <v-app>
        <v-app-bar>
            <v-col cols="12" align="end"> 
                <!-- <v-btn to="/">home</v-btn>
                <v-btn to="/login">login</v-btn>
                <v-btn to="register">register</v-btn> -->
                <v-btn v-for="(x, index) in listbutton" :key="index"
                :to="x.link"
                :text="x.title"
                :color="x.color"
                >
                </v-btn>
            </v-col>
          
        </v-app-bar>
        <v-main>
            <slot />
        </v-main>
    </v-app>
</template>


<script setup>

const listbutton = ref([
    {link: '/', title: 'home', color: 'red'},
    {link: '/login', title: 'login', color: 'green'},
    {link: 'register', title: 'register', color: 'orange'}
])


</script>

